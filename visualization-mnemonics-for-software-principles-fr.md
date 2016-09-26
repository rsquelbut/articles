# http://www.daedtech.com/visualization-mnemonics-for-software-principles/
Cet article est une traduction d'un article de Erik Dietrich paru ici


# traduction

Peut-être, parce que vous souhaitez vous mêler à des discussions sur le développement informatique sans avoir besoin de rechercher subrepticement des définitions sur votre téléphone, ou bien parce que vous avez bientôt un entretien avec une entreprise pour un poste de d'expert OOP ou autre chose, mais vous désirez être bien informés sur le monde du développement et ses principes de fabrication. C'est probablement doublement vrai pour vous qui prenez le temps de lire des blogs sur le monde du logiciel.

A travers l'écriture de ce poste, j'aimerais vous fournir quelques techniques rapides pour apprendre les principes de développement et vous permettre ainsi de vous en rappeler plus tard. On va le faire en racontant quelques petites histoires. Aller c'est parti.

## Loi de Demeter

La semaine dernière, je voyageais tranquillement au volant de ma voiture quand je me suis arrêté à la station service pour me dégourdir les jambes et m'acheter une boisson rafraîchissante. Je prends la canette dans le frigo, la pose sur le comptoir, 
attendant que le caissier me dise "c'est $1,95". A ce moment naturellement, j'enlève mon pantalon. Là le garçon menace d'appeler la police et hurle à l'indécence. Alors, confus, j'explique 

> Mais je suis justement en train d'essayer de vous payer. 
> Regardez : je vous tends mon pantalon, vous fouillez dans les poches, 
> jusqu'à trouver mon portefeuille, vous le sortez et prenez l'argent nécessaire. 
> S'il y a trop, remettez la monnaie dans le portefeuille *unless it's a coin* , 
> puis vous le remettez dans la poche du pantalon, enfin vous me rendez le pantalon. 

Il sort, alors  un fusil depuis derrière le comptoir et m'informe que dans son magasin, 
on obéit à la loi de Demeter *or else*.

en.wikipedia.org/wiki/Law_of_Demeter

Mais que dit la loi de Demeter ? Notamment, elle dit 

> donnez à vos collaborateurs exactement ce qu'ils demandent 
> et ne leur fournissez pas quelque chose qu'ils font devoir parcourir pour obtenir ce qu'ils cherchent.

C'est la raison pour laquelle on ne tend pas au caissier notre pantalon (ou même notre portefeuille) mais qu'on lui donne directement l'argent. Ce n'est pas malin de l'envoyer fouiller à la recherche de l'argent. La loi de Demeter vous encourage à penser pareil pour votre code. Ne présentez pas votre pantalon au client de votre méthode en le forçant à chercher ce qui l'intéresse en invoquant `Pants.Pockets[1].Wallet.Money`, donnez lui directement `Money`. Et si vous êtes le caissier, n'acceptez pas qu'on vous tende un pantalon pour le fouiller à la recherche de l'argent, demandez l'argent ou sortez votre fusil.

## Single Responsibility Principle

Il y a peu de temps, ma femme et moi avons effectué un investissement immobilier. Il s'agit d'une petite maison, construite dans les années 50. Bien qu'agréable et charmante, elle ne propose pas toutes les commodités modernes que j'aurais bien appréciées. Ainsi, je vais devoir me lancer dans quelques petits chantiers, refaire les sols, construire quelques trucs et en détruire d'autres. Ce genre de bricoles.

J'avais ainsi prévu d'installer un système d'élimination des déchets comprenants 2 composants: plomberie et électricité. La partie plomberie est relativement simple dans le sens où il suffit d'enlever le tuyau de vidange existant et d'insérer le nouveau dispositif entre la vidange et le tuyau. La partie électricité est plus intéressante. En effet, il fallait mettre en place un interrupteur permettant d'allumer ou d'éteindre ce dispositif. Naturellement, je n'ai pas eu envie de créer tout un circuit depuis le compteur général juste pour cet interrupteur. J'ai donc décidé d'en utiliser un qui était déjà là. L'interrupteur de l'entrée a la responsabilité d'allumer ou éteindre la lumière de cette entrée. Mais je lui ajouté une autre fonction, celle de contrôler ma nouvelle corbeille.

Et ça fonctionne super bien. Jusqu'alors nous n'avons eu un seul petit problème, un jour que je vidais des plats et une cuillère est tombée dans le dispositif alors qu'à ce moment précis, ma femme a allumé la lumière de l'entrée pour accueillir les invités que nous attendions. Heureusement, je n'ai eu à déplorer qu'une éraflure mineure et une cuillère inutilisable. 
C'est un petit prix à payer pour éviter de créer tout un nouveau circuit. Mais réellement, est-ce le pire qu'il pourrait arriver ?

Nous sommes bien d'accord que la pire chose qui puisse arriver serait que quelqu'un perde la main à cause de cette conception absurde. Parce que vous êtes allés à l'encontre du _Principe de Responsabilité Unique_, que l'on pourrait décrire vaguement comme 

> faire une seule chose mais le faire bien 

ou bien 

> n'avoir qu'une seule raison de changer 

Ici, nous avons 2 raisons d'utiliser l'interrupteur : allumer le broyeur ou éclairer l'entrée, ce qui crée un problème évident. Le parallèle avec le code est aussi vrai. Si vous avez une classe qui doit être changée lorsque le schéma évolue ou lorsque la GUI évolue, alors vous avez une classe qui sert 2 maîtres et il est possible que les évolutions 
pour une contrainte affectent l'autre. L'espace disque n'est pas très cher et les _classes/namespaces/modules_ sont des ressources renouvelables. Alors dans le doute, créez en un nouveau.


## Open/Closed Principle

Je n'ai pas trop eu le temps de regarder la télé ces derniers jours, principalement parce que la télé est un gros consommateur de temps. C'était beaucoup plus simple lorsque la télé ne diffusait qu'un signal analogique qui venait des airs. Mais est venu le temps du digital. J'ai donc du trafiquer ma télé et la recabler pour qu'elle traîte le signal numérique. Le pire dans tout ça, c'est quand je me suis fâché avec le fournisseur de cable et que nous avons changé de fournisseur *(DISH ??)*, j'ai alors du retravailler sur la télé. Maintenant, nous avons une Nintendo Wii, un lecteur de DVD et un *Roku*, et j'aimerais savoir qui a le temps de reprendre sa télé et la recabler pour qu'elle traite chacun de ces nouveaux objets ? Et comme si ce n'était pas assez, j'ai essayé, l'an dernier de "brancher" une vieille Sega MasterSystem et mon *Dish* a cessé de fonctionner.

… Jamais personne n'a fait ça. Pour la bonne et simple raison que personne n'énonce jamais que cette télé que vous avez commandée respecte le Open/Closed Principle. Ce qui signifie que vous devez fabriquer des composants qui sont fermés à la modification mais ouverts à l'extension. Les télévisions que vous achetez ne sont pas faites pour être démontées par vos soins et j'imagine que personne ne conçoit devoir trifouiller les entrailles de la télé juste pour brancher un composant. C'est pour éviter celà que les cables et connecteurs Coax/RCA/Component/HDMI/etc ont été créés. Ses connecteurs et le fait qu'elle soit scellée sous garantie font que votre télévision est ouverte à l'extension mais fermée à la modification. Vous pouvez étendre ses capacités en branchant le périphérique de votre choix, voire même des composants qui n'existent pas encore, commme par exemple une X-Box 12. Suivez donc le même principe pour avoir du code flexible. Lorsque vous écrivez du code efforcez vous de maximiser la flexibilité en facilitant la maintenance à travers les extensions et du nouveau code. Si vous programmez à travers des interfaces et que vous laissez la possibilité de modifier le comportement à travers l'héritage, la vie sera beaucoup plus simple qund viendra l'heure du changement. Je vous invite donc à suivre ce principe plutôt que d'écrire la grosse classe mastodonte que vous allez devoir tenter de comprendre puis modifier à chaque sprint. C'est dégueu et vous allez finir par la détester cette classe ainsi que sa conception. De la même manière que vous détesteriez la télévision que j'ai décrite un peu plus haut.


## Liskov Substitution Principle

J'ai généralement pour habitude de dîner une salade assez classique. Vous savez, genre salade, tomates, croutons, oignons, carottes et cigüe. En revanche, je fais une chose originale quand je mange ma salade. A chaque coup de fourchette j'examine chaque élément avant de le mettre dans ma bouche (beaucoup d'amateurs de salades composées vont beaucoup plus vite mais jouent avec leur vie). Pour ce faire, je déroule un algorithme simple. Si l'ingrédient que j'ai dans ma fourchette n'est pas de la cïgue, alors je le mange. Si c'est de la cigüe, je le repose dans un coin de mon assiette pour le jeter plus tard. Je vous recommande chaudement de manger votre salade de cigüe de la sorte.

Ou bien, vous pouvez garder en tête le principe de subsitution de Liskov. Ce principe explique que si vous avez une relation d'héritage, alors chaque dérivé devrait pouvoir être remplacé par leur type de base. Ainsi, dans ma salade de *comestibles*, je ne devrais pas avoir un type dérivé *cigüe* qui ne se comporte pas de la même façon que les autres *comestibles*. Une autre façon de voir les choses est d'imaginer une collection d'objets hétérogènes dans une hiérarchie d'héritage, vous n'allez pas dans ce cas, parcourir les éléments les uns après les autres et vous demander 

> voyons de quel type est celui-ci et adaptons notre traitement

Alors suivez le LSP et ne composez de la salade à la cigüe pour personne. Vous aurez du code plus propre et vous éviterez la prison.

## Interface Segregation Principle

Dieu soit loué le cache de pages web, ça sauve des vies. Dès que j'interroge mon dictionnaire en ligne préféré, expertbeginnerdictionary.com (ce n'est pas un vrai site, pour ceux qui pensaient le visiter), on me demande un mot à rehercher, dès que le je saisis, alors il m'envoie le dictionnaire à travers HTTP, alors grâce à Ctrl-F, je peux chercher mon mot. Mais ca prend un temps terrible à mon navigateur de charger le dictionnaire entier, je serais vraiement peine s'il n'y avait pas ce mécanisme de cache. Bon, le seul problème, c'est qund un mot du dictionnaire change. Alors le cache est invalidé et ma prochaine recherche prendra le temps de recharger en entier ce dictionnaire. Haaa si, si seulement il y avait une meilleur façcon de faire.

… Pourtant il y en a un. Ne me renvoie pas tout le dictionnaire dès que je cherche un mot. Juste la définition de ce mot. Si je veux savoir ce qu'est un *zèbre*, je me moque de connaître la signification de *aardvark*. En revanche ma recherche de *zèbre* ne sera pas affectée par un quelconque changement sur le mot *aaedvark*. Ma recherche ne devrait être dépendante que des mots et définitions que j'utilise au même moment, mais jamais de tout le dictionnaire. De la même façon, si vous définissez des interfaces publiques à destination de vos clients, découpez les en parties les plus petites possibles et composables. Laissez à votre client le soin de les assembler comme bon lui semble, plutôt que de le forcer à composer avec le tout (ou dictionnaire)
[le *kitchen sink* (ou dictionnaire)]. Le ISP précise qu'il ne faut pas forcer les clients d'une interface à dépendre d'une méhode dont ils n'ont pas besoin, à cause de certains *****. Donne à ton client le minimum requis.
(The Interface Segregation Principle says that clients of an interface shouldn’t be forced to depend on methods that they don’t use because of the excess, pointless baggage that comes along.  Give clients the minimum that they need.
)

## Dependency Inversion Principle (DIP)

Avez vous déjà visité une usine automobile ? C'est incroyable de voir la façon dont elles sont fabriquées. On commence avec une voiture et la voiture assemble son, moteur, ses sièges, ses roues, etc... C'est vraiment incroyable à observer. Si vous voulez vous régaler, regardez ces sous-parties sassembler leurs propres composants internes. Par exemple,  le moteur construit son alternateur, sa batterie, sa transmission. Un coup de génie de l'industrie. Bien sûr, il y a un inconvénient à tout et aussi cool que celà puisse paraître, celà doit-être un peu frustrant pour les ouvriers qui n'ont aucun contrôle sur ce moteur que la voiture s'est construite pour elle-même. Tout ce qu'ils peuvent faire, c'est dire

> je veux une voiture

et la voiture fait le reste.


Je parie que vous pouvez imaginer la base de code que je décris. Il y a longtemps, j'étais rentré dans les détails à propos de cette alégorie,  but je vais résumer ici en disant qu'il s'agit du pattern "commande et contrôle" où les constructeurs d'objet instancient tous les objets dont ils dépendent. Ainsi le FooService instancie son propre logger. Cette façon de faire va à l'encontre du DIP, qui implique que les modules de haut niveau, comme Voiture par exemple, ne doivent pas dépendre des modules de bas-niveau, comme le Moteur, mais devrait plutôt dépendre d'une abstraction comme l'interraction Voiture-Moteur. Cela permet de modifier indépendamment le moteur ou la voiture, ce qui signifie que nos mécaniciens peuvent décider de quel moteur va dans quelle voiture. Comme décrit dans le lien, une base de code construite en respectant ce principe tend à être composable, alors que celle basée sur le pattern "Commande et Contrôle" ne le sera pas, favorisant l'approche "voiture, constuit toi toi-même". Pour comprendre et vous souvenir du DIP, demandez vous qui doit contrôler quelles parties sont utilisées dans la construction de la voiture ? Les gens qui construisent la voitre ou bien la voiture elle-même ? Une de ces deux idées est absurde.

…Cinq des principes décris ici, composent les principes SOLID. Pour en savoir plus sur le sujet, vous pouvez consulter les cours Pluralsight sur le sujet.
