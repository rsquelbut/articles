# http://www.daedtech.com/visualization-mnemonics-for-software-principles/
Cet article est une traduction d'un article de Erik Dietrich paru ici


# traduction

Peut-être, parce que vous souhaitez vous mêler à des discussions sur le développement informatique sans avoir besoin de rechercher subrepticement des définitions sur votre téléphone, ou bien parce que vous avez bientôt un entretien avec une entreprise pour un poste de d'expert OOP ou autre chose, mais vous désirez être bien informés sur le monde du développement et ses principes de fabrication. C'est probablement doublement vrai pour vous qui prenez le temps de lire des blogs sur le monde du logiciel.

A travers l'écriture de ce poste, j'aimerais vous fournir quelques techniques rapides
pour apprendre les principes de développement et vous permettre ainsi de vous en rappeler plus tard.
On va le faire en racontant quelques petites histoires. 
Aller c'est parti.

## Loi de Demeter

La semaine dernière, je voyageais tranquillement au volant de ma voiture
quand je me suis arrêté à la station service pour me dégourdir les jambes 
et m'acheter une boisson rafraîchissante. 
Je prends la canette dans le frigo, la pose sur le comptoir, 
attendant que le caissier me dise "c'est $1,95". 
A ce moment naturellement, j'enlève mon pantalon. 
Là le garçon menace d'appeler la police et hurle à l'indécence. 
Alors, confus, j'explique 

> Mais je suis justement en train d'essayer de vous payer. 
> Regardez : je vous tends mon pantalon, vous fouillez dans les poches, 
> jusqu'à trouver mon portefeuille, vous le sortez et prenez l'argent nécessaire. 
> S'il y a trop, remettez la monnaie dans le portefeuille *unless it's a coin* , 
> puis vous le remettez dans la poche du pantalon, enfin vous me rendez le pantalon. 

Il sort, alors  un fusil depuis derrière le comptoir et m'informe que dans son magasin, 
on obéit à la loi de Demeter *or else*.

en.wikipedia.org/wiki/Law_of_Demeter

Mais que dit la loi de Demeter ? 
Notamment, elle dit 

> donnez à vos collaborateurs exactement ce qu'ils demandent 
> et ne leur fournissez pas quelque chose qu'ils font devoir parcourir pour obtenir ce qu'ils cherchent.

C'est la raison pour laquelle on ne tend pas au caissier notre pantalon (ou même notre portefeuille) 
mais qu'on lui donne directement l'argent. 
Ce n'est pas malin de l'envoyer fouiller à la recherche de l'argent. 
La loi de Demeter vous encourage à penser pareil pour votre code. 
Ne présentez pas votre pantalon au client de votre méthode 
en le forçant à chercher ce qui l'intéresse en invoquant 
`Pants.Pockets[1].Wallet.Money`, donnez lui directement `Money`. 
Et si vous êtes le caissier, n'acceptez pas qu'on vous tende un pantalon 
pour le fouiller à la recherche de l'argent, demandez l'argent ou sortez votre fusil.

## Single Responsibility Principle

Il y a peu de temps, ma femme et moi avons effectué un investissement immobilier. 
Il s'agit d'une petite maison, construite dans les années 50. 
Bien qu'agréable et charmante, elle ne propose pas toutes les commodités modernes que j'aurais bien appréciées. 
Ainsi, je vais devoir me lancer dans quelques petits chantiers, 
refaire les sols, construire quelques trucs et en détruire d'autres. Ce genre de choses.


J'avais ainsi prévu d'installer un système d'élimination des déchets comprenants 2 composants: plomberie et électricité. 
La partie plomberie est relativement simple dans le sens où il suffit d'enlever le tuyau de vidange existant 
et d'insérer le nouveau dispositif entre la vidange et le tuyau. 
La partie électricité est plus intéressante. 
En effet, il fallait mettre en place un interrupteur permettant d'allumer ou d'éteindre ce dispositif. 
Naturellement, je n'ai pas eu envie de créer tout un circuit depuis le compteur général juste pour cet interrupteur. 
J'ai donc décidé d'en utiliser un qui était déjà là.
L'interrupteur de l'entrée a la responsabilité d'allumer ou éteindre la lumière de cette entrée. 
Mais je lui ajouté une autre fonction, celle de contrôler ma nouvelle corbeille.

Et ça fonctionne super bien. 
Jusqu'alors nous n'avons eu un seul petit problème, 
un jour que je vidais des plats et une cuillère est tombée dans le dispositif alors qu'à ce moment précis, 
ma femme a allumé la lumière de l'entrée pour accueillir les invités que nous attendions. 
Heureusement, je n'ai eu à déplorer qu'une éraflure mineure et une cuillère inutilisable. 
C'est un petit prix à payer pour éviter de créer tout un nouveau circuit. 
Mais réellement, est-ce le pire qu'il pourrait arriver ?

Nous sommes bien d'accord que la pire chose qui puisse arriver serait que quelqu'un perde la main 
à cause de cette conception absurde. Parce que vous êtes allés à l'encontre du 
_Principe de Responsabilité Unique_, que l'on pourrait décrire vaguement comme 

> faire une seule chose mais le faire bien 

ou bien 

> n'avoir qu'une seule raison de changer 

Ici, nous avons 2 raisons d'utiliser l'interrupteur : allumer le broyeur ou éclairer l'entrée, 
ce qui crée un problème évident. Le parallèle avec le code est aussi vrai. 
Si vous avez une classe qui doit être changée lorsque le schéma évolue ou lorsque la GUI évolue, 
alors vous avez une classe qui sert 2 maîtres et il est possible que les évolutions 
pour une contrainte affectent l'autre. 
L'espace disque n'est pas très cher et les _classes/namespaces/modules_ sont des ressources renouvelables. 
Alors dans le doute, créez en un nouveau.

## Open/Closed Principle

I don’t have a ton of time for TV these days, and that’s mainly because TV is so time consuming. It was a lot simpler when I just had a TV that got an analog signal over the air. But then, things went digital, so I had to take apart my TV and rewire it to handle digital signals. Next, we got cable and, of course, there I am, disassembling the TV again so that we can wire it up to get a cable signal. The worst part of that was that when I became furious with the cable provider and we switched to Dish, I was right back to work on the TV. Now, we have a Nintendo Wii, a DVD player, and a Roku, but who has the time to take the television apart and rewire it to handle each of these additional items? And if that weren’t bad enough, I tried hooking up an old school Sega Genesis last year, and my Dish stopped working.

Je n'ai pas trop eu le temps de regarder la télé ces derniers jours, principalement parce que la télé est un gros consommateur de temps. C'était beaucoup plus simple lorsque la télé ne diffusait qu'un signal

