# récupération du container

```bash
$ docker pull docker-vsct.pkg.cloud.socrate.vsct.fr/dtproduit/product-catalog:demo_jvm_docker
$ docker tag docker-vsct.pkg.cloud.socrate.vsct.fr/dtproduit/product-catalog:demo_jvm_docker
 demo
```

# par défaut
```bash
$ docker run --rm -ti -e JAVA_OPTS="-XX:+PrintFlagsFinal" -p 50080:8080 --name demo demo
$ docker stats demo --no-stream
$ docker logs demo | grep MaxHeapSize
$ numfmt --to=iec-i --suffix=B --padding=7 <size>
```
Le container prends 100% de la mémoire du host.

La JVM prends environ 25% de la mémoire du container.

# sizé à 256m
```bash
$ docker run --rm -ti -e JAVA_OPTS="-XX:+PrintFlagsFinal" --memory=256m -p 50080:8080 --name demo demo
$ docker stats demo --no-stream
$ docker logs demo | grep MaxHeapSize
$ numfmt --to=iec-i --suffix=B --padding=7 <size>
```
On voit que la mémoire de la heap JVM n'a pas bougé. 

__ATTENTION des problèmes d'allocation de mémoire risquent grandement de survenir__

Jusqu'à la version 1.8u141, par défaut la jvm calcule la taille du système sur le host au lieu du conteneur. 

A partir de la jdk 1.8u131, le jdk propose une option pour déclarer qu'il se trouve sur un conteneur et donc va chercher les paramètres systèmes du conteneur:

> -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap

Il est prévu que cette option soit prise en compte automatiquement dans de futures releases.


# prise en compte des cgroups
```bash
$ docker run --rm -ti -e JAVA_OPTS="-XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal" --memory=256m -p 50080:8080 --name demo demo
$ docker logs demo | grep MaxHeapSize
$ numfmt --to=iec-i --suffix=B --padding=7 <size>
```
la heap est maintenant de 128m (256/2)

La bonne pratique est de fixer soit-même le xmx. 

La tentation est grande, pour maximiser le nombre de containers de fixer xmx = container size. Mais attention, selon [Oracle](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html
 "Oracle")
> The -Xmx option is equivalent to -XX:MaxHeapSize.

Y a-t-il de la mémoire allouée en dehors de la Heap ?

# comment se répartit la mémoire java ?

```
$ docker run --rm -ti -e JAVA_OPTS="-XX:NativeMemoryTracking=summary -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal"  --memory=256m  -p 50080:8080 --name demo demo
$ docker exec demo jcmd 1 VM.native_memory summary
$ numfmt --to=iec-i --suffix=B --padding=7 --from-unit=1024 <sizes>
```
Ajout de l'option (jamais en prod)
> -XX:NativeMemoryTracking=summary

description bloc par bloc de la mémoire (surtout heap, gc, classes, thread)

[Native Memory Tracking categories](https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/tooldescr022.html#BABCBGFA
 "Categories")

[Oracle example](https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/tooldescr007.html#BABGFJDJ
 "Oracle")

Et si on essayait de jouer avec les GC ?

# exemples avec différents GC

```
$ docker run --rm -ti -e JAVA_OPTS="-XX:+UseG1GC -XX:NativeMemoryTracking=summary -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal" --memory=256m -p 50080:8080 --name demo demo
$ docker exec product-catalog jcmd 1 VM.native_memory summary
$ docker run --rm -ti -e JAVA_OPTS="-XX:+SerialGC -XX:NativeMemoryTracking=summary -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal" --memory=256m -p 50080:8080 --name demo demo
$ docker exec product-catalog jcmd 1 VM.native_memory summary
```

le serial prend quelques kb, le G1 quelques 10Mb.

# hyper optimisation

``` 
$ docker run --rm -ti -e JAVA_OPTS="-XX:+UseSerialGC -XX:MinHeapFreeRatio=20 -XX:MaxHeapFreeRatio=40 -Xss256k -XX:NativeMemoryTracking=summary -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal" --memory=256m -p 50080:8080 --name demo demo
``` 

par rapport à avant, on passe d'environ 141Mo de committed à 66Mo.
