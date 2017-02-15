Cet article est une traduction d'un article de Erik Dietrich donnant quelques moyens mnémotechniques pour se rappeler de bons principes de développement. La version originale est parue ici : [visualization mnemonics for software principles][original].

# Introduction

Vous aimez participer aux discussions techniques de vos collègues sur le développement logiciel, mais généralement vous devez trop souvent regarder votre téléphone en cachette pour comprendre tous les concepts de la discussion. Ou alors peut-être avez-vous réussi à obtenir un entretien pour un poste de leader technique. Ce qui est sûr, c'est que vous aimez comprendre votre environnement de travail et faire votre métier de manière qualitative. Pour celà, vous vous efforcez de rester bien informés sur le monde du développement et ses principes de fabrication. Par exemple, en lisant des blogs sur les bonnes pratiques de développement.

A travers l'écriture de ce post, j'aimerais vous fournir quelques techniques rapides pour apprendre les principes de développement et vous permettre ainsi de les mettre en pratique plus tard. On va le faire au travers de quelques saynètes.

## Loi de Demeter

La semaine dernière, je voyageais tranquillement au volant de ma voiture quand je me suis arrêté à la station service pour me dégourdir les jambes et m'acheter une boisson rafraîchissante. Je vais chercher la canette dans le frigo, la dépose sur le comptoir, attendant que le caissier me dise 

> c'est $1,95 

A ce moment, naturellement, j'enlève mon pantalon. Mais là, le mec menace d'appeler la police et hurle à l'indécence. Alors, confus, j'explique 

> Mais je suis justement en train d'essayer de vous payer. Regardez : je vous tends mon pantalon, vous n'avez qu'à fouiller les poches jusqu'à trouver mon portefeuille, le sortir et prendre l'argent nécessaire. S'il y a trop, remettez la monnaie dans le portefeuille, puis vous le remettez dans la poche du pantalon et enfin vous me rendez le pantalon. 

A ce moment là, il sort un fusil de derrière le comptoir et m'informe que dans son magasin, on obéit à la [loi de Demeter][demeter_wiki] ou bien on s'en va.

![illustration][demeter_pic]

Mais que dit la loi de Demeter ? Entre autre, elle dit 

> donnez à vos collaborateurs exactement ce qu'ils demandent et ne leur fournissez pas quelque chose qu'ils vont devoir inspecter à la recherche de ce dont ils ont besoin.

C'est la raison pour laquelle on ne tend pas au caissier notre pantalon (ou même notre portefeuille) mais qu'on lui donne directement l'argent. Ce n'est pas pertinent de lui faire fouiller vos affaires à la recherche de l'argent. La loi de Demeter vous encourage à faire de même pour votre code. Ne présentez pas votre pantalon au client de votre méthode en le forçant à chercher ce qui l'intéresse en invoquant `Pants.Pockets[1].Wallet.Money`, donnez lui directement `Money`. Et si vous êtes le caissier, n'acceptez pas qu'on vous tende un pantalon pour le fouiller à la recherche de l'argent, demandez l'argent ou sortez votre fusil.

## Single Responsibility Principle - SRP

Il y a peu de temps, ma femme et moi avons effectué un investissement immobilier. Il s'agit d'une petite maison construite dans les années 50. Bien qu'agréable et charmante, elle ne propose pas toutes les commodités modernes dont j'aimerais bien profiter. J'ai donc du me lancer dans quelques petits chantiers, refaire les sols, construire quelques trucs et en détruire d'autres. Ce genre de bricoles.

J'avais ainsi prévu d'installer un système d'élimination des déchets. Celui-ci se compose de deux parties : la partie plomberie et la partie électricité. La partie plomberie est relativement simple dans le sens où il suffit d'enlever le tuyau de vidange existant et d'insérer le nouveau dispositif entre la vidange et le tuyau. La partie électricité est plus intéressante puisqu'il fallait installer un interrupteur permettant d'allumer ou d'éteindre ce dispositif. Naturellement, je n'ai pas eu envie de créer de toute pièce un nouveau circuit allant du compteur général jusqu'à ma cuisine, juste pour cet interrupteur. J'ai donc décidé d'en utiliser un qui était déjà là : l'interrupteur de l'entrée. Celui-ci sert à allumer ou éteindre la lumière de l'entrée justement. Mais je lui ajouté une autre fonction; celle de contrôler mon broyeur.

Et ça fonctionne super bien. Jusqu'à aujourd'hui nous n'avons eu un seul petit problème, un jour où nous recevions des amis pour le repas. Je vidais les épluchures du repas que nous venions de préparer lorsqu'ils ont sonné. Ma femme s'est dépêchée de les accueuillir et a allumé la lumière de l'entrée au moment précis où j'ai fait tomber une cuillère dans le dispositif. Heureusement, je n'ai eu à déplorer qu'une éraflure mineure et la perte d'une cuillère. Finalement, c'est un petit prix à payer en comparaison de l'installation d'un tout nouveau circuit électrique. Mais pensez-vous réellement, qu'il s'agit du pire qu'il puisse m'arriver ?

Nous sommes bien d'accord que la pire chose qui puisse arriver, serait que l'un d'entre nous perde la main à cause de cette conception absurde. Parce que vous êtes allés à l'encontre du _SRP_, que l'on pourrait décrire grossièrement comme 

> faire une seule chose mais la faire bien 

ou bien 

> n'avoir qu'une seule raison de changer 

Or ici, nous avons 2 raisons d'utiliser l'interrupteur : allumer le broyeur ou éclairer l'entrée. Ca crée un problème évident. Et le parallèle avec le code est vrai. Si vous avez une classe qui doit être changée lorsque le schéma évolue ou encore que la GUI évolue, alors vous avez une classe qui sert 2 maîtres. Dans ce cas, il est possible que les évolutions induites par une contrainte affectent l'autre responsabilité. Comme l'espace disque n'est pas très cher et que les _classes/namespaces/modules_ sont des ressources renouvelables, dans le doute, n'hésitez pas, séparez.


## Open/Closed Principle - OCP

Je n'ai pas trop eu le temps de regarder la télé ces derniers jours. Pour une bonne raison : ma télé est un gros consommateur de temps. C'était très bien quand la télé ne diffusait qu'un simple signal analogique qu'on captait depuis la prise murale. Mais est venu le temps du digital. J'ai donc du trafiquer ma télé et la recabler pour qu'elle traite le signal numérique. Le pire c'est quand je me suis fâché avec mon fournisseur d'accès et que nous sommes passés chez *DISH (fournisseur de télé par cable américain)*, j'ai encore du rebricoler ma télé. Maintenant, nous avons une Nintendo Wii, un lecteur de DVD et un *Roku (lecteur de streaming)*. Entre nous, j'aimerais vraiment savoir qui a le temps de modifier sa télé et de la recabler pour qu'elle sache traiter chacun de ces nouveaux terminaux ? Mais comme j'aime le challenge, j'ai essayé, l'an dernier de *brancher* une vieille Sega MasterSystem. Mon terminal *Dish* n'a pas supporté, il a cessé de fonctionner.

…Sachez-le, jamais personne n'a fait ça. Pour la bonne et simple raison que personne n'explique jamais que votre télé a été conçue en respectant l'OCP. Ce principe signifie que vous devez fabriquer des composants qui sont fermés à la modification mais ouverts à l'extension. En d'autres termes, les télévisions ne sont pas prévues pour que vous les bricoliez vous-même. J'imagine aussi que personne ne conçoit devoir trifouiller les entrailles de sa télé juste pour brancher un composant. C'est d'ailleurs pour éviter celà que les cables et connecteurs Coax/RCA/Component/HDMI/etc ont été créés. Ces connecteurs et le fait que la télé soit scellée sous garantie induisent que votre télévision est ouverte à l'extension mais fermée à la modification. Vous pouvez étendre ses capacités en branchant le périphérique de votre choix, voire même en branchant des composants qui n'existent pas encore, commme par exemple une X-Box 12. Je vous invite à suivre le même principe pour avoir du code flexible. Lorsque vous codez, efforcez vous de maximiser la flexibilité en facilitant la maintenance à l'aide d'extensions. Si vous programmez à l'aide d'interfaces ou que vous permettez de modifier le comportement à travers l'héritage, la vie sera beaucoup plus simple qund viendra l'heure du changement. Allez dans ce sens plutôt que d'écrire la bonne grosse classe *qui fait tout* et que vous allez devoir comprendre puis modifier à chaque sprint. C'est dégueu et vous allez finir par la détester cette classe. Sa conception aussi. De la même manière que vous détesteriez la télévision décrite au dessus.


## Liskov Substitution Principle - LSP

Le soir, j'aime manger léger. J'ai donc pour habitude au dîner, de manger une bonne salade bien classique. Vous savez, le genre de salade avec des tomates, des croutons, de l'oignon, des carottes et de la cigüe. Du coup, je mange ma salade d'une façcon assz particulière : a chaque coup de fourchette j'examine les éléments dans ma fourchette avant de la mettre dans ma bouche (beaucoup d'amateurs de salades composéesnvont beaucoup plus vite mais jouent avec leur vie selon moi). Pour ce faire, je déroule un algorithme simple. Si l'ingrédient que j'ai dans ma fourchette n'est pas de la cigüe, alors je le mange. Si c'est de la cigüe, je le repose dans un coin de mon assiette pour le jeter plus tard. Selon moi, c'est la seule façon sûre de manger votre salade de cigüe.

Ou alors, vous pouvez penser au LSP. Ce principe explique qu'en cas de relation d'héritage, alors chaque dérivé devrait pouvoir être remplacé par son type de base. Ainsi, dans ma salade de *comestibles*, je ne devrais pas avoir un type dérivé *cigüe* qui ne se comporte pas de la même façon que les autres *comestibles*, c'est à dire qu'il m'empoisonne. Autre cas, imaginons une collection d'objets hétérogènes dans une hiérarchie d'héritage. Vous n'allez pas dans ce cas, parcourir les éléments les uns après les autres et vous demander 

> voyons de quel type est celui-ci puis adaptons le traitement

Alors respectez le LSP et ne préparez jamais une salade à la cigüe. Pour personne. De cette façcon, vous aurez du code plus propre et vous éviterez la prison.

## Interface Segregation Principle - ISP

Dieu soit loué le caching de pages web !!! Ca sauve des vies !!! Dès que je visite mon dictionnaire en ligne préféré, *expertbeginnerdictionary.com* (ce n'est pas un vrai site, pour ceux qui pensaient le visiter), on me demande un mot à rechercher. Dès que le je saisis, alors il m'envoie le dictionnaire à travers le réseau, puis avec Ctrl-F, je peux rechercher ma définition. Le problème, c'est que le navigateur mets un temps terrible à charger le dictionnaire en entier. Ca serait vraiment pénible sans ce mécanisme de cache. Le problème, c'est quand un mot du dictionnaire change. Dans ce cas, le cache est invalidé et ma prochaine recherche devra recharger le dictionnaire complet. Si seulement il y avait une meilleure façon de faire !!!

Et oui, il y en a un. Ne renvoie pas tout le dictionnaire dès que je cherche un mot. Renvoie juste la définition de ce mot. Si je veux savoir ce qu'est un *zèbre*, je me moque de connaître la signification de *aardvark*. En plus, ma recherche de *zèbre* ne sera pas affectée par un quelconque changement sur le mot *aaedvark*. En principe, ma recherche ne devrait être dépendante que des mots et définitions que j'utilise au même moment, mais jamais de tout le dictionnaire. Pareil, si vous définissez des interfaces publiques à destination de vos clients, essayez de les découper en parties les plus petites possibles et composables entre elles. Et laissez à votre client le soin de les assembler comme bon lui semble, plutôt que de le forcer à composer avec le tout (ou le dictionnaire). L'ISP précise qu'il ne faut pas forcer les clients d'une interface à dépendre d'une méhode dont ils n'ont pas besoin. Donne à ton client le minimum requis.

## Dependency Inversion Principle - DIP

Avez-vous déjà visité une usine automobile ? C'est incroyable de voir la façon dont est assemblée une voiture. On part d'un chassis puis la voiture assemble son moteur, ses sièges, ses roues, etc… C'est vraiment incroyable à observer. Si vous voulez vous régaler, regardez ces sous-parties assembler elles-même leurs composants internes. Par exemple, le moteur construit son alternateur, sa batterie, sa transmission. C'est un coup de génie de l'industrie. Bien sûr, il y a un inconvénient à tout. Et aussi cool que celà puisse paraître, ça doit-être quand même un peu frustrant pour les ouvriers de n'avoir aucun contrôle sur ce moteur que la voiture s'est construite elle-même. Tout ce qu'ils peuvent faire, c'est dire

> je veux une voiture

et la voiture fait le reste.

Je parie que vous imaginez la base de code que je décris. Il y a longtemps, j'ai filé cette métaphore dans l'article [ici][ioc]. Ici je vais résumer en disant qu'il s'agit du pattern "commande et contrôle" où les constructeurs d'objets instancient tous les objets dont ils dépendent. Ainsi le FooService instancie son propre logger. Cette façon de faire va à l'encontre du DIP. Le DIP préconnise que les modules de haut niveau, comme *Voiture* par exemple, ne doivent pas dépendre des modules de bas-niveau, ici le *Moteur*. Ils devraient plutôt dépendre d'une abstraction, ici ça serait l'interraction *Voiture-Moteur*. Cela permet de modifier indépendamment le moteur ou la voiture. Ca signifie que nos mécaniciens peuvent décider de quel moteur va dans quelle voiture. Comme décrit dans le lien, une base de code construite en respectant ce principe tend à être composable. Alors que celle basée sur le pattern "Commande et Contrôle", favorisant l'approche "voiture, construis toi toi-même", ne le sera pas. Pour bien intégrer le DIP, demandez vous qui doit décider des morceaux à embarquer dans la construction de la voiture ? Les gens qui construisent la voiture ou alors la voiture elle-même ? Attention, une de ces deux idées est absurde.


…Cinq des principes décrits ici, composent les principes SOLID. Pour en savoir plus sur le sujet, je vous invite à consulter les cours Pluralsight sur le sujet.

[original]: http://www.daedtech.com/visualization-mnemonics-for-software-principles/ "visualization mnemonics for software principles"
[demeter_pic]: http://www.daedtech.com/wp-content/uploads/2014/06/PantlessLawOfDemeter.jpg  "Illustration de la loi de Demeter"
[demeter_wiki]: en.wikipedia.org/wiki/Law_of_Demeter "loi de Demeter"
[ioc]: http://www.daedtech.com/inverting-control/ "Inverting control"
