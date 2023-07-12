# Introduction
Vous trouverez dans le dossier [data](https://github.com/YGautier/powerz-bi-technical-test/tree/main/data) les trois tables dont vous aurez besoin pour ce test technique :
* [__users__](https://github.com/YGautier/powerz-bi-technical-test/blob/main/data/users.csv) contient des informations sur des utilisateurs fictifs, à savoir :
	* *user_uid*, un identifiant unique attribué à la création du compte de l'utilisateur,
	* *country*, le pays de l'utilisateur.
* [__game_data__](https://github.com/YGautier/powerz-bi-technical-test/blob/main/data/game_data.csv) contient des informations sur les sessions de jeu effectuées par ces utilisateurs, à savoir :
	* *user_uid*, l'identifiant unique de l'utilisateur ayant effectué la session et défini dans la table __users__,
	* *start_dt*, la date de début de session,
	* *end_dt*, la date de fin de session,
	* *platform*, la plateforme sur laquelle la session a été effectuée.
* [__chimera_data__](https://github.com/YGautier/powerz-bi-technical-test/blob/main/data/chimera_data.csv) contient enfin des informations sur le premier type de chimère débloqué par chacun des utilisateurs listés. Il est en effet demandé aux utilisateurs de faire un choix durant leur expérience de jeu entre 5 types de chimères, et, si les utilisateurs ont la possibilité de débloquer tous les types de chimères, ils doivent en débloquer au moins 1 afin de pouvoir progresser dans l'histoire[^1]. Cette table contient donc les colonnes suivantes :
	* *user_uid*, l'identifiant unique de l'utilisateur concerné et défini dans la table __users__,
	* *first_unlocked_chimera*, le premier type de chimère débloqué par l'utilisateur.
[^1]: A titre purement informatif, si vous essayez de faire une partie avec la version du jeu actuelle, vous remarquerez que cette information est aujourd'hui obsolète, la logique de récupération des chimères ayant un peu changé.  

Pour chacune des questions suivantes, il sera demandé de justifier votre raisonnement. En particulier, il vous sera demandé de joindre le code permettant d'extraire les données utilisées dans votre justification (par exemple, si vous avancez qu'une session dure en moyenne 12 minutes sur iOS, nous vous demandons de joindre le code vous permettant d'arriver à cette conclusion à partir des tables proposées). Etant donné qu'une majorité du travail proposé dans l'offre de stage s'effectuera à l'aide de requêtes à des bases de données, une grande préférence est donnée à l'utilisation d'un langage de requête type SQL de votre choix (MySQL, PostgreSQL, Clickhouse, etc.). Si vous ne trouviez cependant pas de façon satisfaisante d'obtenir des résultats que vous jugez nécessaires pour répondre à une question, tout autre langage vous permettant d'avancer sera également accepté.

# Wx
Une métrique que nous utilisons régulièrement est *Wx*, définie comme le nombre de joueurs ayant effectué au moins une session entre 7x et 7x+6 jours après leur première session. Par exemple, un utilisateur se reconnectant 19 jours après sa première session contribuera à W2 (puisqu'il s'est connecté entre 7\*2=14 et 7\*2+6=20 jours après sa première session).

1. A partir des tables données, indiquez les valeurs de W1 et W4 pour chacun des pays représentés.
2. Toujours à partir de ces mêmes tables, donnez toutes les valeurs de Wx pour x compris entre 0 et 4 inclus pour chacune des plateformes de jeu utilisées.
3. A votre avis, dans quel but nous servons-nous de cette métrique ? Quelles en seraient selon vous les forces et les faiblesses ?

# Types de chimères
Comme indiqué ci-dessus, lors de leur expérience de jeu, les joueurs sont confrontés à un choix concernant le "type" de leur chimère, c'est-à-dire grossièrement l'élément qui leur sera associé. La question est la suivante :

4. A partir des tables données, déterminez si tous les types de chimères disponibles semblent être choisis de manière équitable. A titre informatif, les données ayant été générées aléatoirement, nous avons fait en sorte que l'intervalle de confiance soit largement suffisant pour pouvoir conclure sans le moindre doute.

# Notions de statistiques
Nous souhaitons maintenant analyser le temps total de jeu de nos utilisateurs. La question est la suivante :

5. Nous recherchons une à deux métriques simples dont nous pourrons facilement suivre l'évolution au jour le jour. Compte tenu des données en votre disposition, quelles métriques pourriez-vous nous proposer et pour quelles raisons ?
