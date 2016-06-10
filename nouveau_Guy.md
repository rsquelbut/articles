# le nouveau Guy

Qui est Guy ? Guy c’est le nouveau développeur qui vient renforcer votre équipe. C’est peut-être aussi le nouveau scrum master qui vient améliorer vos processus. Mais Guy, c’est aussi le nouvel expert technique qui vient instaurer les bonnes pratiques de développement.

## introduction

L’arrivée d’une nouvelle personne dans une équipe n’est jamais anodine. Pourtant, dans de nombreuses organisations où les employés sont considérés comme des ressources, cela est traité comme tel. C’est dommage, car lorsqu’une équipe se connaît bien, elle a atteint sa vélocité nominale. Bien souvent un équilibre s’est créé, chaque personne a noué une relation avec chaque coéquipier. Les forces et les faiblesses de chaque personne se compensent. 
Cette équipe est devenue une unité.

Intégrer quelqu’un dans cette équipe a toute les chances d'abimer son équilibre et diminuer sa vélocité. Dans le meilleur des cas, il est souhaitable que l’équipe soit demandeuse d’un renfort et qu’elle soit partie prenante du processus de recrutement. Il est de notoriété publique que les équipes les plus efficaces sont les plus autonomes sur les plans techniques et méthodologiques. C’est à dire quand ils ont le choix de leur outil de travail.  

De la même façon, il est important lors du processus de recrutement, d’aborder aussi bien les aspects négatifs que les aspects positifs de la mission. Ainsi pas de mauvaise surprises lors de l’arrivée du nouveau. Pas de déception inutile, ni d’un côté ni de l’autre.

De mon côté, j’ai toujours été plus attiré par ceux qui me proposaient la réalité que ceux qui me semblaient l’offusquer.

## le recrutement

Le processus de recrutement ne doit pas être une étape commerciale mais une première étape de collaboration. Le but n’est pas forcément de séduire un super technicien intransigeant, mais plutôt de trouver la personne adéquate qui se fondra dans son environnement. Sauf s’il y a un besoin de révolution dans l’équipe bien sûr ;)

__Présenter un contexte de travail réaliste permettra de sélectionner des candidats réalistes.__

Un collègue m’a donné le conseil de répéter le plus de fois possible le mot « test unitaire » dans les entretiens de mission afin d’être sûr de tomber dans un environnement où les TU seront appréciés à leur juste valeur. Je trouve ce conseil très judicieux et surtout représentatif de ce que je viens d’énoncer.

Ainsi, pour bien présenter les forces et les faiblesses de l’équipe et de la mission, quoi de mieux qu’un futur coéquipier ?
Dans la même idée, n’est il pas plus naturel de mieux accueillir quelqu’un qui nous a séduit lors d’un entretien qu’une personne que l’on a jamais vu ?
Heureusement, cette pratique est déjà bien généralisée. Mais on pourrait aller encore plus loin, en organisant pourquoi pas une heure ou deux de pair programming avec un coéquipier rompu à cet exercice.

## les premiers jours

Mais une fois que le nouveau coéquipier est là, comment bien l'accueillir ? Je veux dire, mieux qu’avec quelques sourires :)

Le jour de son arrivée, avoir un ordinateur, des accès (physiques comme numérique) et ne pas l'oublier semble le minimum. Malheureusement, ce minimum n'est pas toujours respecté. Dans ce cas, plutôt que de faire potasser une documentation probablement désuète, optez pour le pair programming ou quelques jours de « vis ma vie de [stakeholder|expert métier|marketing|testeur] » (voir plus loin). 

De même, avoir préparé son arrivée en dégageant du temps à quelques personnes de l’équipe pour l’aider dans ses premiers pas/jour est très agréable pour le nouvel arrivant. 

Mais pourquoi ne pas essayer d’aller plus loin ?

D’un point de vue personnel, je ne crois pas qu’il faille appliquer un même processus pour toute arrivée. En effet, accueillir un développeur chevronné qui va encadrer une équipe n’est pas la même chose qu’accueillir un junior dans une équipe qui tourne. Les contextes peuvent être multiples selon le niveau général de l’équipe, l’ambiance qui y règne, le niveau du recruté et surtout ce qu’on attend de lui : encadrer / mettre en place des bonnes pratiques / être une force supplémentaire de l’équipe / être une future force vive de l'équipe

## les recettes simples

Cependant un certain nombre de recettes marchent à tous les coups : 

- avoir une application avec des tests unitaires bien sûr

- avoir un build portable. C’est à dire que, une fois nos outils de développement installés, il suffit d’importer le projet dans notre IDE et tout compile. Pas besoin de suivre un wiki de 4 pages expliquant comment configurer le workspace, le serveur d'appli pour compiler et builder le projet.

- faire des revues de code. Si les revues de code ne sont pas mises en place chez vous, c’est une pratique simple à mettre en place et efficace tout le temps. Encore plus important lors d’une arrivée, cela permet de vérifier que le travail du nouvel arrivant concorde avec les pratiques appliquées au sein de votre équipe. En effet les bonnes pratiques ne sont pas les mêmes partout. Ainsi le feedback sera très rapide. Cela est primordial dans le cas de l’intégration d’un junior. Celui ci commettra probablement toutes les erreurs que vous même avez pu commettre à vos débuts. Il ne s’agit pas de blâmer ces erreurs mais de lui faire comprendre pourquoi elles sont des erreurs. Dans le cas de l’arrivée d’un senior cela vous permettra d’apprendre de nouvelles choses, mais surtout cela fera naître des discussions permettant à chacun de s’approprier encore mieux le code existant et futur.

- commencer par du pair-programming : cette technique permet d’onboarder rapidement un nouveau sur tous les plans : technique, méthodologique, fonctionnel en attaquant directement des sujets de fond. Cela permet en outre de favoriser la relation entre le nouveau et chaque partenaire de pair. Attention, tout de même au pair-programming intensif. D’une part parce que c’est très fatiguant (sauf si celui qui ne tient pas le clavier sommeille). D’autre part, il est important aussi de faire ses propres expériences seul pour mieux intégrer certains concepts. Cette option permet presque de justifier l'absence d’un poste de travail fonctionnel à l’arrivée du nouveau.

- rapidement former sur le métier. Après quelques jours/sprints de développement, il est important de former fonctionnellement le nouvel arrivant. Lui expliquer les grands principes qui sous-tendent le métier, mais dégagés de la complexité accidentelle liée à la technique. Et oui tout le monde ne fait pas du DDD ou du BDD. Et pour coder une application qui répond au besoin, il faut comprendre au mieux ce métier et les besoins qui en découlent. 

## les recettes plus relevées
Ces méthodes précédentes sont relativement classiques et connues, mais j’ai connu d’autres initiatives très intéressantes :

- dans ma mission actuelle, on commence par un exercice de développement sur l’application cible. Il s’agit d’ajouter un nouveau service à l’application, cet exercice permet de toucher des couches les plus hautes aux couches les plus basses de l’application. Un sorte de bac à sable pour faire ses premiers pas. L’exercice se termine par une review complète effectuée par un membre confirmé de l’équipe. 

- organiser des sessions de « vis ma vie de …». Il s’agit de passer, par exemple, une semaine avec les gens du marketing lorsque nos stakeholders travaillent pour le marketing. Celà permet d'aborder nos futurs développements avec un autre point de vue. Un ami recruté au service marketing chez l'Oréal a passé ses 6 premiers mois comme démarcheur pour bien comprendre et connaître les besoins des clients et vendeurs de ses futurs produits. Ce cas est bien sûr un peu extrême, mais très illustratif de l'idée. Chez Atlassian, les développeurs prennent parfois la place des testeurs pendant 1 semaine ou deux. Ou encore des graphistes. Celà permet de mieux prendre en compte les besoins et impératifs de chacun lors du développement. Voyez les explication de Samuel Le Berrigaud à ce propos  -> https://www.parleys.com/tutorial/developper-en-mode-kick-ass

- faire quelques jours de mob-programming, c’est à dire tout l’équipe derrière un seul PC. Un collègue coach, ayant récemment mis en place cet exercice, m’en a récemment expliqué les bienfaits. Dans des équipes rencontrant des soucis de communication, cela permet de faire remonter très rapidement des points de vue non exprimés et donc ressassés. Dans ce genre d’exercice, les discussions deviennent rapidement sincères. Le nouveau pourra apprécier plus rapidement le caractère de ses coéquipiers. Attention toutefois a ne pas dépasser 2 ou 3 jours car pendant ce temps la vélocité est quasi nulle.

## du plus simple au plus compliqué

Il est plus facile d’enrichir son savoir avec des sujets proches de ce que l’on connait déjà. 

Fonctionnellement, il est conseillé d'aller du plus général au plus spécifique. Les principes généraux sont plus simples à comprendre. Une fois ceux-ci intégrés, on peut s'y raccrocher comme à une branche lorsque l'on aborde les spécificités et autres exceptions métiers.

Techniquement en revanche, l’apprentissage se fera naturellement du bas vers le haut. On va d'abord comprendre la méthode puis la classe, puis la hiérarchie d'appel, le module, le service, etc... Attention, celà ne veut pas dire qu'il faut jeter à la poubelle, le petit schéma d'architecture de l'applications avec 3 flèches. S'il y a 25 flèches, gardez le pour plus tard !!

## des bénéfices pour l’équipe ?

L’équipe peut aussi profiter de l’arrivée d’un nouveau Guy pour remettre en cause ses process et méthodes. Lorsqu’un problème est rencontré, une solution est proposée. Cette solution est plus ou moins convenable. Mais avec le temps, il se peut que le problème n’existe plus, ou bien ait changé de forme à tel point que la solution retenue à l’époque soit devenue inopérante, voire même contre productive. Alors pourquoi continue-t-on à appliquer cette solution dépassée ? Tout simplement la force de l’habitude. Il faut donc profiter de l’arrivée d’un Guy, de ses yeux neufs et ses interrogations légitimes. 
Si l’on n’a pas d’autres arguments que 

> Le processus de livraison est trop compliqué ? C’est carrément mieux qu’avant pourtant !!!

ou encore 

>  Je ne sais plus pourquoi on a cette stacktrace dans l'appli c'est pas grave, elle ne gêne pas

Alors il est temps de remettre en cause ces mauvaises habitudes ou de réparer ces fenêtres cassées !!!
Profitez de la venue de ce nouveau Guy pour remettre aux propres vos habitudes ou vous rappelez le pourquoi de vos décisions. De plus on est jamais à l'abri d'une bonne idée.

## le turn over

Plus le turn-over est important dans votre entreprise, plus cette phase d’onboarding sera importante, afin de minimiser les pertes de temps et d'argent à chaque "transfert de compétences". De l’autre côté, meilleur sera votre onboarding, plus grandes seront les chances de fidéliser vos développeurs. En effet, travailler sur ce processus d’onboarding permet de prendre conscience des forces et des faiblesses de l’équipe. Et travailler dans une équipe consciente est très agréable. Ainsi, naturellement le turnover diminuera. Vous le voyez bien, il est temps de réfléchir à votre onboarding.

## mauvaise pioche

Malgré tout le soin qu'on a pu apporter au recrutement, il peut s'avérer que le nouveau Guy ne convienne pas. 

Parfois, le candidat n'a pas laissé paraître son manque d'intérêt lors de la présentation de la mission, ou bien a-t-il été "forcé" par son entreprise. 

Parfois, il s'agit d'incompatibilité de caractères ou de cultures. Un ami trop humble ne s'est ainsi pas plu dans une atmosphère compétitrice. Il avait besoin de se sentir aidé plutôt que poussé dans ses retranchements pour donner le meilleur de lui même. Mais celà dépend de chacun. Celà ne sert alors à rien d'insister et de continuer à perdre du temps.

# conclusion

Pour des conseils de plus haut niveau, Je vous conseille fortement de vous intéresser à la Living Documentation. Cette discipline est totalement axée sur la transmission du savoir avec le moins d'effort possible. Elle exige en revanche une collaboration serrée de tous les interlocuteurs liés à l'application. Lors de la formation Living Documentation que j'ai suivie, Cyrille Martraire présentait une documentation protéiforme de l'application. A partir des annotations dans le code, on pouvait extraire une doc s'apparentant à un parcours découverte des différents services. On pouvait aussi ne découvrir que les classes s'apparentant à un concept du métier. Par exemple tout ce qui est lié à la prise de commande pour un site de e-commerce. Puis tout ce qui est lié aux réductions. Ces idées excellentes, ne sont possibles à mettre en place, que si cette documentation est générée automatiquement.

Pour terminer, un petit rappel, tout le monde préfère travailler dans un environnement de travail propre. C’est pareil pour les développeurs avec leur code. L'intégration d'un nouveau sera toujours simplifiée si le code applicatif et les outils sont standards. Soignez donc votre codebase et suivez les préceptes du clean code -> https://cleancoders.com/videos
