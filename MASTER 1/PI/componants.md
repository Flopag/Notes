# Explication des composants de Lingwal

## Préface

Ces explications sont basées uniquement sur mon expérience avec le projet intégré Lingwal. Je ne prétends pas être un expert en composants. Cette approche a très bien fonctionné pour nous, mais elle ne convient peut-être pas à tous les projets.

Le texte a été rédigé par moi, puis corrigé grammaticalement avec l'aide de ChatGPT.

## Qu'est-ce qu'un composant ?

Un composant est une boîte noire qui propose des interfaces et utilise celles d'autres composants.  
En tant que boîte noire, il n'expose que ses fonctionnalités via des interfaces bien définies, tandis que son fonctionnement interne est caché et isolé du reste du système.  
Cela permet aux composants d'être indépendants, n'interagissant entre eux qu'à travers ces interfaces.  
Un composant est donc défini uniquement par ce qu'il fait, et non par la manière dont il le fait.  
Cette abstraction permet de changer l'implémentation d'un composant sans affecter le reste du système, tant que les interfaces restent intactes.

## Quel est l'intérêt des composants ?

Puisque les composants sont des boîtes noires définies par leurs interfaces, il suffit de spécifier ces interfaces, et leur implémentation est indépendante.  
Par exemple, si un composant nécessite des modifications ou des améliorations, cela peut être fait sans impacter les autres composants du système.  
Ce découplage permet également à plusieurs équipes de travailler en parallèle, chacune sur des composants distincts, sans avoir besoin de connaître les détails des autres parties du système.  
Cela allège considérablement la collaboration en équipe, réduit les risques de conflits lors de l'intégration et favorise l'indépendance des développeurs.

Prenons l'exemple de l'ajout d'une nouvelle fonctionnalité dans mon projet : si nous avons besoin d'un nouveau type de donnée ou d'une nouvelle manipulation,  
il suffit de créer un nouveau composant qui implémente cette fonctionnalité, sans toucher aux composants existants.  
Cela rend le système très évolutif et permet d’ajouter ou de retirer des fonctionnalités rapidement.

En outre, comme les interfaces sont définies à l'avance, le code est bien structuré, ce qui simplifie la production.  
C'est étonnant de voir à quel point on peut accomplir des tâches complexes de manière simple lorsque l'on est bien organisé.

## Les composants de Lingwal

![](attachments/Components.png)

## Explication des composants

Dans un diagramme UML, les composants sont représentés par des rectangles.  
Les cercles pleins représentent les interfaces définies, et les demi-cercles représentent les interfaces nécessaires.  
Par exemple, le composant **OAuth Proxy** implémente une interface qui permet de récupérer un token et utilise l'interface d'**Auth** pour obtenir ce token.

Avant de commencer, on peut identifier cinq catégories : **Web Client**, **Computation Server**, **Management Server**, **MongoDB**, et **MySQL**.  
Elles indiquent dans quel pod les composants sont implémentés, mais pour l'instant, nous pouvons faire abstraction de cela.

### La data et les manipulateurs de données

Il y a deux composants qui stockent des données : **MongoDB Database** et **SQL Database**.  
Le premier est utilisé pour stocker des fichiers, et le second pour les autres types de données.

Huit composants manipulent les données : **Is Authorized On**, **Tree**, **Question**, **Sheet**, **Locality**, **User**, **Document**, et **Contribution**.  
Chaque composant correspond à un type de donnée stocké dans la base de données.  
On peut les identifier en consultant le modèle ER des bases de données.

L'élément clé est que seuls les manipulateurs de données peuvent interagir avec les bases de données.  
Comme les données sont fragiles et peuvent être facilement corrompues, il est crucial que leur manipulation soit contrôlée avec rigueur.  
Chaque manipulateur de données ne peut manipuler que les données qui lui sont attribuées.  
Par exemple, le manipulateur de **User** ne peut traiter que les utilisateurs.  
Si ce dernier doit interagir avec les contributions, il demandera au manipulateur de **Contribution**, mais ne le fera pas lui-même.  
Cela garantit que tant que chaque manipulateur fait correctement son travail, les données sont robustes et non corrompues.

Cette approche permet également une gestion simplifiée de la sécurité et rend le code plus évolutif.  
Si un nouveau type de donnée est nécessaire, il suffit de créer un nouveau composant dédié, et le reste du système continue de fonctionner sans interruption.

### Les gestionnaires (managers)

Les gestionnaires sont : **OAuth Proxy**, **Auth**, et **Computation**.  
Ils gèrent les aspects qui ne sont pas directement liés à l'application mais qui sont indispensables à son bon fonctionnement.

- **OAuth Proxy** redirige l'utilisateur vers le SSO de l'ULiège et donne un cookie pour identifier le client et l'utilisateur. Il établit également une connexion chiffrée entre le client et le serveur.
- **Auth** associe le client et l'utilisateur, puis vérifie que l'utilisateur est légitime avant de rediriger la requête vers la destination souhaitée.
- **Computation** lance des processus de calculs et renvoie les résultats.

Ces gestionnaires sont invisibles pour l'utilisateur final, qui ne leur envoie jamais de requêtes directement.  
Ils fonctionnent comme la poste : ils prennent la requête, la manipulent et la transmettent au destinataire.

### Les utilisateurs

Les utilisateurs sont : **UI**, **Exporter**, **Analyzer**, et **Importer**.  
Ils utilisent l'application et ont tous le même niveau d'accès.

- **UI** représente l'interface utilisateur (le front-end du site).
- **Exporter**, **Analyzer**, et **Importer** sont des composants back-end. Ils réalisent des calculs sur demande et retournent une réponse à **Computation**.

Chaque utilisateur utilise les mêmes interfaces pour interagir avec le système, ce qui garantit une cohérence et une sécurité accrues dans l'ensemble du processus.

## Explication des 5 pods

Il y a 5 pods :

- **Web Client** : fournit l'UI au client et n'a accès qu'au **Management Server**.
- **Computation Server** : exécute tous les calculs nécessitant beaucoup de ressources et n'a accès qu'au **Management Server**.
- **MongoDB** : héberge la base de données MongoDB. Seul le **Management Server** y a accès.
- **MySQL** : héberge la base de données MySQL. Seul le **Management Server** y a accès.
- **Management Server** : gère la manipulation des données, leur intégrité et leur sécurité. Tous les autres pods doivent être authentifiés pour y accéder.

Avoir plusieurs pods améliore la sécurité, répartit la charge de travail et limite les impacts en cas de panne d'un pod, car seul un redémarrage partiel est nécessaire.

## Collaboration et organisation d’équipe

Chaque équipe peut se concentrer sur un composant spécifique, ce qui réduit le risque de conflits lors de l'intégration et facilite le développement parallèle.  
Les interfaces définies à l'avance aident à une meilleure coordination.

## Conclusion

Les composants n'ont pas besoin d'être parfaits, leur modularité permet de les améliorer, remplacer ou réparer individuellement.  
Cette approche améliore la sécurité, les performances, et la flexibilité, tout en favorisant une organisation efficace du travail en équipe.
