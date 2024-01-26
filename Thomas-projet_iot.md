# Sujet DevOps : Projet d'objet connecté (IoT)

## Contexte Initial

Notre entreprise est une société de création d'outils de diagnostique dans le contrôle qualité.
Nous fournissons à nos clients des produits de haute qualité, et nous sommes reconnus pour notre expertise dans le domaine de la mesure de la qualité de l'air. 
Mais nous agissons également dans d'autres domaines, comme la mesure de la qualité de l'eau, ou encore la mesure de la qualité des sols, l'étude de la biodiversité, etc.

Nous avons développé un outil central permettant d'intéragir avec tous nos produits, et de les configurer. Cet outil est un logiciel de bureau, qui permet de configurer les différents paramètres de nos produits, de les mettre à jour, de les calibrer, etc.
Récemment, nous avons décidé de nous lancer dans le développement d'une application mobile, qui permettra, dans un premier temps, à nos clients de configurer nos produits depuis leur téléphone portable. Cette application mobile sera disponible sur Android et iOS.

Nous utilisons un langage unique: Javascript par le biais de typescript.
Le projet est donc par défaut accessible par le web. Mais également, par le biais de React Native, il est possible de créer une application mobile à partir de nos ressources communes.
De la même manière, Electron est utilisé pour créer une application de bureau à partir de nos ressources communes.

Nous avons un besoin constant de nouveau collaborateurs. Nous avons de nombreux outils pour nous aider à nous développer et nous recrutons essentiellement des développeurs seniors full stack Javascript qui ont déjà utilisé React Native et Electron.

Nous avons découpé nos équipe en 5 squads de 10 developpeurs. Chaque squad possède 1 Product Owner, 1 Scrum Master, 1 Lead Dev, 1 QA.
Nous avons une équipe de DX (Developer Experience) qui s'occupe de la mise en place des outils de développement, de la formation des développeurs, de la mise en place des bonnes pratiques, etc.
C'est dans cette équipe que vous officierez.

## Problématique

Nous avons beaucoup de petits projets, tous stockés dans des repositories différents.
Certaines de nos fonctionnalités nécessitent de faire des modifications dans plusieurs repositories différents. Nous aimerions pouvoir gérer ces modifications de manière centralisée, et pouvoir les déployer de manière centralisée.

Actuellement, si l'on modifie un repository, il faut faire une pull request, attendre la validation, puis faire une release, puis attendre la validation, puis déployer, puis attendre la validation.
Et seulement après, il faudrait faire la même chose pour les autres repositories concernés par la modification.

Si je modifie le firmware du capteur d'air. Il faudra changer l'application mobile, l'application desktop, le backend, et le frontend web.

Nous avons également de plus en plus de mal à intégrer nos développeurs sur la partie front. Certains réclames des documentations ou des tests mais notre QA ne fait que des tests physiques et n'a pas le temps de faire des tests automatisés.
Sur le back et l'electronique les développeurs utilisent des tests unitaires mais sur le front rien n'est fait.

Et finalement, nous avons beaucoup de mal à analyser les erreurs rencontrées par nos utilisateurs. Nous avons des outils de monitoring qui fonctionne bien. Mais nous aimerions pouvoir avoir des informations plus précises sur le code qui ne fonctionne pas, retours d'erreurs, etc...
Nous avons souvent des cas liés à des versions de navigateurs, ou des versions de systèmes d'exploitation, ou encore des versions de firmwares. Mais aussi des problèmes de connexions. Nous aimerions pouvoir avoir des informations plus précises sur ces cas là.

## Objectif de Modernisation

L'objectif est donc de rassembler tout nos projets dans un seul repository.
Nous souhaiterions des propositions sur l'amélioration :
- du workflow de développement (éviter les npm link et les PR de sous projets)
- de la qualité du code et d'un code beaucoup plus homogène
- éviter les regressions
- automatiser le plus de choses possibles
- avoir une documentation à jour