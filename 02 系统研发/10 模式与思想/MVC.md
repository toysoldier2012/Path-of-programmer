#mvc

MVC est un patron d'architecture, il sépare l'application en trois composants principaux, le modèle, le vue et le contrôleur.

====Le modèle==== est en charge de gestion des données et les logiques. 
On peut le subdiviser en certains parties:
- La couche DAO, contient les opérations CRUD, ces dernières sont des traitements très basiques et très proche de BDD. Elle est un abstraction de couche persistance.
- La couche Repository, est un abstraction de collection d'objets. Elle contient un ou plusieurs DAO, puis les cumule ensemble.
- La couche service/logic qui se spécialise la gestion des logiques

====Le vue==== se concentre sur l'affichage

====Le contrôleur==== est une liaison entre les deux parties précédentes, il gère l'échange des informations 


entity
JavaBean
POJO
domain