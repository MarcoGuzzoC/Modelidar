# Modelidar
> ***Projet MODELIDAR 2022 conception d'une plateforme motorisée et acquisition des données d'un LIDAR via ROS***

![picture](/assets/images/Capture_d_écran_2022-06-17_090028-removebg-preview.png)


## Présentation générale du projet : 

Le projet de la première année à l’ENSEA vise à développer un ensemble de compétences nécessaires à l’aboutissement d’un projet. Celles-ci comptent des savoir managériaux (répartition des étapes, gestion des équipes…) et techniques (Conception, développement…). 

Pour notre groupe, le professeur encadrant (qui fait office de chef de projet) a opté pour une voiture télécommandée qui sera équipé d’un LIDAR (light detection and ranging). Ladite voiture devra, une fois achevée, permettre la modélisation 3D des espaces qu’elle parcourt. 

### Aspirations : 

Pour des raisons de contraintes temporelles, le projet sera exécuté par étapes. La première étape est d’établir un prototype fonctionnel qui repondera aux besoins basiques du cahier des charges. Les autres étapes seront des améliorations que nous pourrons apporter au produit pour en optimiser l’utilisation. Celles-ci seront d’aspect esthétique et fonctionnel.  

L’ultime aspiration serait une voiture radiocommandée, capable de scanner son environnement et de transmettre les données à une IHM. 

### Technologies et Hardware disponible : 

- Les technologies mises à disposition par l’encadrant sont : 
- Un LIDAR : Velodyne HI-RES Lidar ;
- Le châssis d’une voiture télécommandée ;
- 2 RaspberryPi 4 ; 
- Une caméra faite exprès pour Raspberry ;
- ROS ;

## Outil ROS : 

L’outil Ros est l’une des technologies choisis pour le projet. Abréviation de Robot Operating System, ROS est un set de librairies et d’outils permettant de créer des applications dédiées pour le contrôle des robots. Sa force réside dans le fait qu’il se base sur une très grande communauté qui se développe continuellement. Cela va faire que son appréhension sera plus facile. D’autre part, l’outil Ros fera en sorte de centraliser l’envoie des données dans une borne commune, chose qui va rendre facile le traitement de cet aspect. 

On fut tous confié en priorité la tache d’étudier cet outil, et plus précisément l’outil Catkin. 
Nous avons donc suivi la procédure et le tutoriel disponible à [l'adresse suivante](http://wiki.ros.org/fr/ROS/Tutorials) 

Notre rôle était de concevoir des noeuds respectivement pour envoyer les données reçues par le joystick pour l'envoyer en réseau à la plateforme mobile et à la commande moteur et du coup un noeud de réception pour cela ; un noeud pour récupérer les données du LIDAR et les envoyer idéalement vers un écran (idéalement). Cependant nous avons rencontré un problème de compatibilité avec nos clés. Etant sur ROS Noetic, nous avions d'abord pensé à faire une installation type *debian* mais à cause de ce souci nous nous sommes finalement tournés vers la version 64bits de *buster* car notre protocole ne fonctionnait que pour cette version et que le nombre de paquet est plus important. 

Utilisation de la machine virtuelle ROS pour réaliser le tutoriel et comprendre comment articuler notre « architecture machine ». Comprendre comment former des nœuds leur envoyer des données et en récupérer est indispensable. Nous avons également cherché et trouvé le package ROS propre à notre LIDAR que nous pourrons implémenter à [cette adresse](https://www.generationrobots.com/blog/fr/integration-dun-lidar-avec-ros-exemples-de-projets/).  

Nous avons donc installé ROS sur plusieurs Raspberry tantôt à cause de crash (court-circuit nape caméra) tantôt parce qu'on avait, a minima, besoin de deux RaspberryPi. En suivant le tutoriel nous avons été jusqu'à la réalisation de la tortue. Elle sera par la suite contrôlée par les joysticks.

##
