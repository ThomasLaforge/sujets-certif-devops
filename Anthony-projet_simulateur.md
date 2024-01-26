# Sujet DevOps : Projet de calculateur/simulateur monolithique

## Contexte Initial

Notre entreprise, opère dans le domaine de la consultation et de la recherche et développement (R&D). Son expertise se concentre sur l'ingénierie de système, le contrôle, l'automatique, la robotique et l'hydrodynamique. Elle est présente dans quatre secteurs industriels majeurs : Parapétrolier, Offshore, Énergies Marines Renouvelables (EMR) et Naval.
L’entreprise, axée sur la production intellectuelle et académique, opère dans le domaine complexe des simulations d'opérations navales en milieu arctique. La culture d'entreprise se caractérise par une forte séparation entre les équipes scientifiques techniques et les responsables de la mise en production. De plus, une partie de l'équipe de recherche, contribuant à la création d'algorithmes de calcul avancés, est internationale, ce qui engendre des disparités dans les pratiques de travail et les conventions de codage.

Son organisation en interne est liée à son fonctionnement, très proche d’un modèle universitaire. Avec les nombreux projets sur lesquels les collaborateurs travaillent, ils ne peuvent s’occuper à plein temps que d’un seul projet à la fois, mais la transversalité des projets induit un échange de connaissances et de techniques permanent. Cependant, de nouveaux projets, aussi bien internes, nécessitent plus de moyens humains, si bien que l’entreprise recrute et est en pleine croissance interne. Les équipes sont donc assez flexibles et indépendantes, ce qui n’empêche aucunement les différents collaborateurs de faire appel les uns aux autres en cas de problème. Cette synergie de connaissances est un véritable moteur pour l’entreprise et la communication entre collaborateurs est un des axes de travail, comme en témoigne la mise en place de réunions hebdomadaires pendant lesquelles on aborde tour à tour les travaux effectués durant la semaine précédente et ceux envisagés pour la semaine actuelle. L’organisation de l’entreprise est donc hybride et les deux facteurs qui y contribuent sont la taille des projets en cours, dimensionnés pour fournir du travail à une personne aux connaissances pointues dans un domaine donné (hydrodynamique, mécanique, traitement du signal, contrôle...) et la communication permanente entre les différents projets. Cette souplesse dans l’organisation des projets permet à n’importe quel moment des micro-interventions entre collaborateurs.

Le secteur de l’énergie est en pleine évolution et l’entreprise profite pleinement de l’apport de fonds, à la fois de l’état et des grandes entreprises du secteur, pour développer des recherches et ses prototypes.

## Énoncé

L’application est un simulateur de structures offshores interagissant avec la glace en mer. L’approche numérique mise en œuvre dans le logiciel SIBIS vise à reproduire avec une haute fidélité des charges de glace et les mouvements des structures offshores, mais dans des charges computationnelles raisonnables. Le moteur de simulation est écrit en C ++, et un ensemble de pré et post-routines de traitement, écrites en C ++ et Matlab. Le moteur de simulation calcule la dynamique de la structure et de la glace, tandis que des routines supplémentaires traitent de tâches telles que la génération de champs de glace, le prétraitement des fichiers d’entrée et le post-traitement des résultats (comme les graphes ou les animations). 

Les premières versions de l’application ont été écrites par un chercheur russe, docteur en modélisation et mécanique de la glace et un senior developer , lui aussi russe, en 2014. Depuis ces première versions, l’app est passé par plusieurs sociétés de consulting en vu d’ajouts de fonctionnalités et d’amélioration. Elle est la propriété d’une société pétrolière norvégienne qui emploie plus 21 000 personnes Les opérations navales en milieu arctique qu’elle mène représentent une charge financière lourde. C’est donc pour éviter d’envoyer des navires en opérations trop dangereuses qu’on souhaiterait les simuler.

Le CTO, en charge du projet, travaille actuellement sur le cœur du moteur physique, les briques logicielles de modélisation de systèmes flottant multi-corps articulés et des liaisons souples de type câble. Pour vérifier la validité de son implémentation et de ses résultats, mais aussi pour préparer les futures améliorations, il souhaite ajouter un module de visualisation. Il a besoin de quelqu’un pour choisir les technologies les plus adaptées à son besoin et commencer la conception du module de visualisation. Il demande de produire un rapport sur les différentes technologies de visualisations envisagées pour savoir laquelle serait la plus adaptée pour le module.

Dans un second temps, vous prendrez le rôle d’un release manager afin d’améliorer le workflow, des dépôt et de la qualité du code en y ajoutant une chaîne de CI/CD automatisée

**Problèmes Actuels :**

1. **Monolithique et Gourmande en Ressources :** L'application fonctionne comme un monolithe sur des ordinateurs gourmands en ressources, entraînant des inefficacités et des coûts élevés.

2. **Processus de Production Archaïque :** Le processus de production est manuel, nécessitant une compilation et un déploiement manuels de la part de l'équipe de développement.

3. **Absence de Tests Automatisés :** L'application n'est pas testée de manière automatisée, ce qui accroît les risques d'erreurs et de dysfonctionnements lors des déploiements.

## Objectif de Modernisation

L'objectif principal est de transformer cette application monolithique en une architecture basée sur des microservices, tout en établissant une chaîne d'outils automatisée pour l'intégration continue (CI) et le déploiement continu (CD). Cette modernisation devrait améliorer l'efficacité, la fiabilité et la gestion des ressources de l'application.



En tant que nouvel(le) ingénieur(e) au sein de notre entreprise, votre mission est de proposer une solution complète pour moderniser notre application et mettre en place une chaîne d'outils automatisée. Considérez les spécificités de notre culture d'entreprise, caractérisée par une forte séparation entre les équipes scientifiques et de production, ainsi que la diversité internationale de nos équipes de recherche.

**Questions pour la Proposition de Solution :**

1. **Décomposition en Microservices :**
   - Quelles fonctionnalités spécifiques de l'application peuvent être transformées en microservices indépendants ?
   - Comment assurer la cohérence et la communication entre les équipes travaillant sur différents microservices ?

2. **Containerisation avec Docker :**
   - Comment Docker peut-il être utilisé pour containeriser chaque microservice ?
   - Comment gérer les dépendances entre microservices dans un environnement Dockerisé ?

3. **Orchestration avec Kubernetes :**
   - Pourquoi Kubernetes est-il essentiel pour orchestrer le déploiement des microservices ?
   - Comment garantir la flexibilité et l'évolutivité des microservices grâce à Kubernetes ?

4. **Chaîne CI/CD Automatisée :**
   - Comment mettre en place une chaîne CI/CD tenant compte de la séparation entre les équipes scientifiques et de production ?
   - Quelles étapes spécifiques doivent être automatisées pour garantir un processus CI/CD fiable ?

5. **Tests Automatisés :**
   - Comment intégrer des tests automatisés à chaque étape du processus CI/CD ?
   - Quels types de tests sont essentiels pour assurer la stabilité des microservices ?

6. **Surveillance et Logging :**
   - Comment mettre en place une surveillance efficace des microservices en production ?
   - Quels mécanismes de logging peuvent aider à identifier rapidement les problèmes potentiels ?
