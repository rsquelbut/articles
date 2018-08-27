# Katas

## Inspiration
- [Arolla via Yammer](https://www.yammer.com/arolla.fr/#/threads/inGroup?type=in_group&feedId=4954106&view=all)
- [Coding Dojo](http://codingdojo.org/kata/)

exemples pour démarrer :
- object calisthenics
- rental movie
- fraction
- red/green/refactor


## Objet calisthenics

### Définition
[les 9 règles](https://gist.github.com/bobuss/6534934)
__pourquoi mon code est sale :__
- est-il maintenable ?
- est-il lisible ?
- est-il réutilisable ?
- est-il testable ?

__calisthenics ??__
La callisthénie (souvent désigné par son nom en anglais calisthenics) est une pratique consistant en un ensemble d'exercices physiques de gymnastique et de musculation visant à l'amélioration des capacités physiques et de l'esthétique du corps.

_On va faire pareil avec la programmation orientée objet._

### ce qu'on peut en retirer :
[you're code sucks let's fix it](https://fr.slideshare.net/rdohms/bettercode-phpbenelux212alternate)

1. une seule indentation par ligne
	- cohesion
	- methodes qui ne font qu'une chose
	- améliore la réutilisabilité
1. ne pas utiliser le mot _else_
	- aide à éviter la duplication
	- rend le code plus clair (un seul chemin)
1. encapsuler les types primitifs et les strings dans des classes _(s'il n'y a pas de compartiment)_
	-   encapsulation des opérations
	-   meilleures définitions des types
1. first class collection
	- implémenter les opérations de filtrage, d'union etc.. dans une seule classe
1. seulement un _'.'_ par ligne (sauf _getter_ ou _fluent_)
	- améliore la lisibilité
	- simplifie le _mock_
	- simplifie les _tests_
	- aide à respecter la loi de _Demeter_
6. ne pas abbrévier
	- une communication + claire
	- met en lumière les problèmes sous-jacents
1. garder des classes petites
	- simple responsabilité
	- renforce l'identité
	- souligne l'intention
1. limiter le nombre de champs dans une classe à 2
	- limiter les dépendances
	- faciliter le mocking pour les tests
1. ne pas utiliser les accesseurs _(getter/setter/...)_
	- évite les erreurs de duplication
	- évite d'exposer le modèle sous-jacent

#### conclusion
__ATTENTION : ces contraintes sont des guides, pas des règles__
- aide à implémenter le saint Graal de la _POO_ : __l'encapsulation des données__
- améliore l'utilisation du polymorphisme _(éviter le else et simplification des conditions logiques)_
- améliore les stratégies de nommage


## Zero bug kata
https://mixitconf.org/2018/zero-bug-kata de Johan Martinsson

La dernière fois on a fait le kata Trivia, que je n'aime pas initialement, mais j'ai changé d'avis après avoir vu la prez de Johan Martinsson sur Zero Bug Kata:
https://mixitconf.org/2018/zero-bug-kata
Ou comment enlever les bugs via un bon design, en évitant d'induire les utilisateurs de votre code en erreur

On était 4 donc on a fait un mob, et à la fin on a trouvé un bug sur la version PHP.


