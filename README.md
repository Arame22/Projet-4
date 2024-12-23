 👉**Présentation du sujet “Prédiction des situations de danger**
Client est une entreprise qui gère le réseau de distribution d’électricité public sur 95 % du
territoire français.
La problématique concerne la sécurité des techniciens. Le technicien travaille en extérieur et
doit respecter un ensemble de procédures par rapport au port de ses EPI (Équipements de
protection individuelle). Nous  sommes amenés à récupérer un ensemble d’informations du type ouverture de vestes, gants non mis … etc à partir de ces informations nous mettrons en place un assistant virtuel capable de lui signaler sa mise en danger. L’IA sera l’élément
différenciant pour s’assurer que dans n’importe quelle situation le technicien sera en sécurité
(portera les équipements de protection nécessaires et indispensables pour la situation).

L’objectif est de mettre en place une solution afin de prédire les instants où un technicien est en danger lors d’une intervention.

😣**La problématique : Comment prédire le risque de danger d’un technicien ?**
L’objectif est de créer un modèle auto-apprenant pour alerter le technicien s’il est en danger
durant une intervention. Il s’agit donc de travailler sur des modèles d’apprentissage non
supervisé permettant de détecter les périodes durant lesquelles un technicien était en
danger, c’est à dire d’alerter le technicien en cas de port non conforme des EPI durant
l’intervention.

🧐**Présentations du jeux de données** 
Pour ce projet, deux ateliers ont été mis en place le 12 et le 22 juillet dans le but de récolter
des données pour répondre à la problématique. Ces ateliers ont permis à des techniciens
d’effectuer des interventions factices.

Dans chaque atelier plusieurs scénarios ont été réalisés, un scénario représentant un
ensemble de manipulations propres à une intervention réelle, par exemple :
● la pose de profilés (qui sont des gaines pour protéger des câbles électriques)
● l’enlèvement de profilés
● la coupure électrique et la vérification d’absence de tension (VAT)
Pour chaque scénarios (interventions), on dispose de deux jeux d’observations, distinguées
à l’aide de la variable “Correct” :
● un dans le cas où le port des EPIs est conforme et
● un dans le cas où le technicien enlève des équipements alors qu’il est censé les
avoir

Ces ateliers ont alimenté une base de données renseignant les EPIs portés à chaque instant
(relevés toutes les 5 secondes) de l’intervention grâce aux capteurs présents sur les pièces
d’équipement
(0 : l’équipement n’est pas mis, 1 : l’équipement est porté et NA : problème du capteur).
On ne prendra pas ici en compte les problèmes de capteurs (les valeurs NA de la base de
données), ceux-ci étant peu nombreux et inexploitables.
Deux techniciens ont participé aux scénarios. Un seul technicien est intervenu pour chaque
scénario (et donc deux modèles d’interventions), on a donc des données différentes suivant
le scénario concerné. Le technicien 1 possède les équipements suivants : casque, visière,
col et gants et le technicien 2 dispose de capteurs sur son casque, sa visière, sa veste et
son col.

Pour l’atelier du 12 juillet, on dispose de 6 scénarios. Parmi ces scénarios, un n’a pas de
données renseignées dans le fichier de prise de note (aucune information sur les moments
où le technicien était en danger) et un présente une erreur dans le déroulement de l’intervention, on dispose donc de 4 scénarios exploitables. C’est à l’étudiant de repérer le
scénario qui présente une erreur dans le déroulement.

Pour celui du 22 juillet, 4 scénarios sont renseignés mais l’un d’entre eux ayant des erreurs
de détection d’équipement trop importantes, on ne l'exploite pas ici.
On dispose ainsi de 7 scénarios (avec 2 expériences chacun) au total.
Ci dessous, les tables 1 et 2 représentent un aperçu des bases de données disponibles :



La variable danger a été ajoutée grâce au fichier de prise de notes fourni et correspond à la variable à prédire.

**La variable Correct est binaire**

