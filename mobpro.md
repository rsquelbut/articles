Cet article est un compte rendu d'un retour d'expérience de Romeu Moura sur la mise en place de mob programming dans sa mission. Entré dans la mission en tant que leader technique, il a obtenu la permission de démarrer sa mission par quelques jours de mob programming, pour prendre plus rapidement la température de son équipe et de son environnement.

# c'est quoi le mob programming
Rapidement, vous connaissez le pair-programming ? C'est codé avec un pair à deux derrière un ordinateur. Bah le mob programming, c'est pareil avec toute l'équipe !!! Oui, oui, je vous assure, toute l'équipe derrière une seule machine.

# le contexte

- L'équipe travaille sur la MCO d'un "GROS legacy de la mort" dixit l'intéressé.
- L'équipe n'est pas anti agilité mais pas encore convaincue des bienfaits de la méthode. Dans le reste de l'open-space, la tendance est pire.
- Un exemple : personne n'est convaincu de l'intérêt du pair programming. Hého, on est plus à la fac les mecs, c'est fini les TD, la glandouille, c'est fini.

# introduction
Premier jour, j'arrive, me présente et propose immédiatement de "faire un mob" pendant une semaine. J'avais convaincu au préalable la chef de projet.

Personne ne connaissait. Donc j'ai expliqué. Devant la modération de l'enthousiasme, ou bien l'épaisseur du scepticisme ambiant, ou les deux, j'ai minoré l'ambition. Réduit la voilure.
Mais, enthousiaste je suis resté :
> les mecs, on commence par une heure de mob. On stoppe, on fait le bilan et on vote pour savoir si on continue toute la journée. Pareil à la fin de la journée, on s'arrête, on fait le bilan, on vote pour continuer le lendemain.

Jeudi et vendredi, on a fait le mob et le vote pour continuer lundi a été rapide : "OUIIIIII"

_____
#jour 1

A la fin de la première journée, les doutes sont encore là, mais l'envie d'en savoir plus aussi. Pour le moment, j'ai simplement réussi à piquer leur curiosité. C'est pas énorme, mais c'est un bon pas. Afin que vous jugiez vous même, voici les  remarques des 4 développeurs à la fin du premier jour :

> C'etait ultra improductif on a rien reussi a coder vraiment et on s'est perdu dans des débats infinis. Mais quand même, j'ai espoir pour demain. Je veux réessayer.

> Moi, ça m'a changé ma routine. J'ai adoré. Carrément je veux réessayer demain.

> Pour ma part, je suis convaincu du format, je veux essayer demain.

> J'ai de forts doutes sur l'exercice et son utilité mais je suis d'accord qu'on ne l'a pas fait assez. Jugeons demain, après la production d'un premier bout de code.


_____
# jour 2

A la fin du deuxième jour, on constate que ce n'est pas très productif au niveau du code, par contre, on dirait que ça réveille l'équipe et qu'elle aime ça :

> Hier on a briefé Romeu sur le contexte. Jusque là, c'était bien. Puis le reste de la journée c'était l'échec. Je suis ici depuis 3 mois, au contraire des autres qui sont là depuis plusieurs années et aujourd'hui on a croisé le seuil où vous me montez en compétence sur le domaine aussi et pourtant c'est le Jour 2, je vote oui pour lundi.

> Aujourd'hui, on a trop parlé et pas assez developpé. J'aimerais que lundi on développe plus lundi, je vote oui.

> On a plus communiqué en 2 jours qu'en plusieurs mois entiers

> Et on sait tous que la communication est notre difficulté principale !!! (rires du reste l'équipe qui acquiesce)l

> Je suis le dev le plus senior de l'équipe, 11 ans juste dans cette équipe. Pourtant j'ai appris des choses aujourd'hui.

_____
# jour 3

La chef de projet part en vacances ce soir, il est 18h15 et je suis en retard pour mon entretien avec elle. Je quitte l'équipe qui me dit :
> bon OK, on continue sans toi du coup

Voici le début de l'entretien : 
> Ils sont partis les autres ? Ils développent sans toi en mob alors que tu n'es plus avec eux ?
> C'est vrai ? Tu veux dire qu'ils sont là, sans toi, dans la salle à coder ?

> Pour tout avouer, personne n'a cru qu'ils ne resteraient la journée entière. On croyait vraiment que ça allait se terminer en conflits.

> Quand tu m'as dit qu'ils ont continué le mob sans toi, les bras m'en tombent !!!

> Je suis verte d'être en vacances la semaine prochaine et pas voir ce que ça donne les autres jours.

> Par contre rassure moi, tu n'a pas l'intention de les convertir au Mob a vie hein ? On s'arrête après une semaine comme on a dit ?

> Ok, un jour encore a mon retour pour que je rejoigne le Mob en PO.

> Oui des Mobs ponctuels après, je veux bien sans souci

___________

"Les autres équipes du projet parlent beaucoup de vous, personne n'a jamais fait rien de pareil ici, déjà que le Pair est vu avec méfiance, tu est un ovni"

"Personne a cru qu'ils resteraient la journée entière, on s'attendais a que ça parte en conflit"

"On a jamais vu quelqu'un prendre une telle place dans une équipe aussi vite, les personnes arrivent, demandent ou est passé cette team, on pointe la salle de reunion tout le monde est surpris"

"Je suis hallucinée de comment tu connais l'équipe, leurs problèmes, axes de travail et trait de personnalité en deux jours"

"il est impossible a toi de savoir ou voir a quel point tu a crée un changement énorme ici en 2 jours"

"2 jours tu te rends compte? 2 jours!"

"quand tu m'a dis qu'ils ont continué le mob sans toi, les bras m'en tombent"

"Je suis verte d'être en vacances la semaine prochaine et pas voir ce que ça donne les autres jours"

"Mais rassure moi: tu n'a pas l'intention de les convertir au Mob a vie hein? on s'arrête après une semaine comme on s'est dit?"

"Oui un jour encore a mon retour pour que je rejoigne le Mob en PO me va"

"Oui des mobs ponctuels après je veux bien sans souci"

-- La CdP, dans notre point avant son départ en vacances


______________

# conclusions

J'étais bien préparé pour mener un Mob après tous ceux que j'avais vécu pendant l'année (Jam de code Arolla, conférences, workshops).  J'imaginais que ce mob avec des développeurs à la papa, non agiles, non craftsmen, qui ne savent pas pairer se dérouleraient selon le scénario suivant : 
 - jour 1 : poubelle
 - jour 2 : thérapie de groupe
 - jour 3 : code, enfin !!!

Au prix d'un certain travail de facilitation, ce fut le cas. 

Pour moi, le jour vraiment important, c'est le jour 2. En fait tu payes les 3 journées complètes pour le jour 2. Et ca vaut le coup !!! Le premier jour est un pré-requis. C'est le chemin vers le deuxième jour. Le troisième jour, est là pour enfin coder. On ne termine pas par une frustration, on finit par quelque de tangible.

Le jour 2, toujours lui, apportera une liste de sujets importants a débattre en équipe. Il fera émerger plein de points de désaccord, d'incomprehension, de vision differente sur comment on fait une tache etc

Le Jours 2 m'a donné un Backlog de points une notre equipe coince, ou les gens doivent appredre de choses, etc etc etc, il m'a donné aussi un fort aperçu de leurs personalités, malheurs etc

Les autres jours de mobs apportent, mais la loi de retours diminués y fit son oeuvre forcement on a bien moins d'infos sur les gens


_____

Pourquoi donc je fais une semaine?

bon déjà : J'ai eu l'pportunité et cela est raison suffisante bien sur! mais quel est mon but?

1 - Me decouvertes humaines maintenat sont plus intimistes, le gars le plus renfermé sur lui de tous (tous très renfermés) commencé a s'ouvrir on y devine un certain nombre de problèmmes personnels a la source de sa demotivation (au Jour 3, je veux dire: putain c'est vraiment beaucoup de decouvertes que prdndraient des mois dans un deai court hein)

2 - Je decouvre le code maintenant, on y code on explore, je vois le legacy, leur capacité a en faire face etc, ma montée en compétence se fait super accelleré (et celle du gars qui est depuis 3 mois au même temps il n'arrete pas de prendre de notes)

3 - Je decouvre leurs axes d'ameilloration techniques, la où je peux les aider etc

4 - ils ont un aperçu de mes compéténces et ce que je peux les apporter qu'aurais pris des mois pour avoir

5 - on fait émérger ce qu'ils ont categorisé dans leur tête comme étant impossible, insurmontable etc : les "murs"

_____

#vendredi:
Moi : "Vu l'état du code et de l'équipe: sans minima 20% de notre charge dedié uniquement au 'ménage' quand je partirai de ton équipe dans gros Max 2 ans la dette sera quand même plus grande que aujourd'hui"

CdP: "tu veux dire en gros un jour par semaine où l'equipe entière ne produit pas sur les tâches clients et vous ne faites que payer la dette technique?"

Moi: "C'est ça, je ne garantis pas que ça c'est assez juste que à moins que ça on est sur de partir dans le mur"

CdP: "Sous réserve que tu sois très transparent sur ce que vous faites ce jour la, je Valide"

#mardi, pendant la retrospective (qu'ils font a chaque 3 semaines)

Moi: "Je propose qu'on se mette en objectif d'ici la prochaine retro de commencer a donner du temps au ménage du code
vu ce qu'on a vu en Mob, pour une modification triviale de 3 lignes on y passe plus d'un jour pour arriver a mettre juste les tests la concernant, ce niveau de dette technique exige un certain combat frontal, Je crois grossomodo qu'il nous faut un Jours par semaine"

DevA : "mais on ne controle pas notre affectation de temps ou priorization c'est la CdP ça"

Moi: "Bien sûr, mais deja discutons si on est d'accord sur l'idée, si on estime que c'est un axe prioritaire, si on voit quoi faire de porductif ce jour la, si un jour c'est trop ou bien pas assez"

Tous les devs: faut le faire

DevA: ce serait en mob

Moi: pas de règle, on le verrait au cas par cas

DevB: je suis le seul a croire qu'on perds du temps a discuter d'une idée qui ne passera juste jamais auprès de nos chefs?

*ça deviens le point le plus voté, de loin, de passant 'on doit communiquer plus'*

Coach facilitant la retro : "bon il me semble que il faut prendre ce point! quelle est la prochaine action, qui prends le point de discuter ça avec la CdP?"

Moi: "C'est fait j'ai parlé avec elle vendredi"

*tout le monde arrete de se regarder entre eux et me fixe immédiatement comme si j'étais un Alien sorti d'un ovni*

*un ange passe*

DevB: et... elle est pour?

_____

Sinon aujourd'hui:
- Suis arrivé en gros rétard (tous les autres jorus a l'heure mais la échec) #lalose
- Ils n'avaient pas commencé sans moi #lalose
- Ils m'attendeaient avec grande envie de leur mob #win
- Pour la première fois en 4 jours de mob je me suis un peu distrait et j'ai perdu le fil d'une tache, en jour 1 j'annonce a tous que c'est inévitable que ça arrive et les dis de prendre une pause sans l'annoncer quand c'est le cas (ils le font) en gros la règle des deux pieds: mais moi je facilite le mob, plus tendu la pause: Ils ont remarqué, m'ont passé le clavier et on essayé de s'organiser pour me ratrapper #enormewin

_____

Hier j'ai mangé avec plusieurs personnes du plateau, dans le chemin de retour un Dev de l'équipe qui fait du C++ et consomme mes services me dit

DevC - "Depuis que tu a joins l'équipe vous faites beaucoup de réunions!"
Moi - "Non on fait un Mob: on dev tous ensemble sur une même machine"
C - "Tu veux dire sur un exercice ou bien sur une vraie tâche?"
M - "Vraie tâche, qu'on essaye de progresser ensemble tous au même temps"
C - "c'est productif ça?"
M - "ça fait émérger les points de desaccords, divergences, mecomprehensions etc dans l'équipe, mais la productivité en soi prends un coup ouais"
C - "ton équipe est celle qui communique le moins dans le plateau, si déjà ça les fait communiquer et que derrière cette communication porte des fruits ça valera le coup"
M - "c'est l'idée"
C - "c'est ton travail ça? faire remonter les équipes? Tu as deja fait beaucoup ça? Tu fait d'autres après?"
M - "Ma mission est les joindre et developper avec eux, la partie de remonter c'est pour donner un kickstart a la chose, mais j'ai bien l'intention d'aller embêter ton équipe aussi vu que vous consommez mes services"
C - "tu est le bienvenu"

_____

sinon

"Comment tu gardes motivation pour te maintenir à jour de Java8, mocking, methodes agiles toussa? Nous on arrive pas" - Le Junior qui n'a que 1 ans d'experience, dont 100% dans cette équipe (ça m'a fait mal au coeur d'entendre ça d'un junior a vrai dire)

_____

"Non mais c'est pourri ce que j'ai fait dans cette classe mais c'est fait comme ça dans 40% de la codebase"
- en une phrase un de mes Devs ouvre a que je parle de payement progressif de dette, ne pas se laisser demotiver par la dette, le concept d'affordabilité dans le legacy la totale

_____


Jour 5 #megalose

Matin hapée par notre coach du coup kata en mob bien cool (je le referai en soiréee c'est pas mal) mais gros stress car on prends du retard sur nos objectifs de la semaine (très reduits au depart en compreension du mob mais existants)

l'aprem grosse suprise deux devs sont happés par une urgence de support (risque prevu au depart comme possible, c'est la vie) et moi et un dev nous sommes happées par une reunion tombé arbitrairement prenant des heures: un seul pauvre dev a conginué seul sur le sujet du mob

du coup demain matin ma question a la foule sera si face a notre reste à faire on continue où l'on splitte le mob

côté cool: j'étais inquiét avant d'arriver sur la mission si on allait avoir une bonne dynamique moi et le coach (c'étais un point soulévé comme a risque) cela s'est confirmé encore 100% faux: chque fois qu'on se voit on se passe la balle tout le temps a mettre l'autre en valeur face à l'équipe c'est un truc de dingue, je me demande si il n'a pas un côté briefing par un de mes collègues :D mais je ne vise personne bien sur Nicolas Fedou

note pour les gens voulant faire des mobs: un mob ça fatigue, se prévoir plein de meetups dans la semaine ou vous facilitez un mob : c'est très con

_____

message de nico fedou
Disons que des tech lead comme toi, énergisant et faisant aussi du team lead, on en voudrait plus souvent (enfin, moi et José, on est fan :-))
On a aussi un objectif de pérennisation de nos coaching (craft et autres), et comme tu semble être "un full agiliste" convaincu...
Après l'opinion du coach, sur le fait qu'on est loin du but et qu'a cette distance, on ne voit pas encore les nuances et qu'il faut te laisser un maximum de place (genre faire un kata en étant observateur seulement) pour que tu puisse te légitimer, ça ne viens que de lui.
Du coup, sur vos objectifs à grosse maille, il est sûr que vous serez toujours d'accord et il ne fera pas de remarque si il n'est pas persuadé que tu sera d'accord...
Bref, c'est intentionnel de sa part et vous avez tout le temps de faire connaissance et je n'y suis pas pour grand chose.

_____

Mais je tiens a donner l'accent sur un point: une tache de kata en mob quleques bons usages
- rechaufer 15 minutes si la team n'est pas reveillé
- expliquer le matin du premier jour (ou en meetup) ce qu'est un mob
- decompresser
- se doner la leçon du kata comme vrai objectif (il y a des ktas que visant nous apprendre un truc X)

Mais ça ne donne pas les effets don je parle dans mes posts ici sur le mob! car le côté interction humaine de l'equipe face a un kata plafone vite! Trop vite!
Prendre les vraies taches de boulot de l'équipe c'est un point essentiel à la magie du truc, un kata c'est ludique, il n'a pas de legacy, il n'a pas de ressenti, il n'a pas de vecu, il n'a pas de pathos

_____

Bon today on a splitté officiellement le mob, comme je ne compte pas hier dans le mob au total on aura fait 4 jours, initialement j'avavais prévu 5, j'ai eu permission pour 7, 4 c'est pas mal

on a splitté car malgré reduction d'objectives on a tout de même des objectives et l'equipe n'aurais pas pu les produire dans la semaine en mob car il y a beaucoup a apprendre chez eux côté travail en equipe, post-split ils ont déjà du mal avec le pair, ne savent pas communiquer avec leur pair, du coup j'ai pairé avec un aujourd'hui

le côté positif c'est que si on a décidé de splitter de manière rationelle, sentimentalement c'etait visible qu'ils avaient cette fois ci vraiment envie d'eviter le split et ont tous communiqué l'envie de finir ASAP leur taches pour essayer de re-MOB demain aprem: on verra
