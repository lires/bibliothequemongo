### Exercice 1.1
#### Recherche par titre:

db.livres.find({ titre: "Le petit chaeperon rouge" }).explain("executionStats")

Nombre de document examiné: 2000
Temps d'éxécution: 6 millisecondes
Type d'étape: COLLSCAN

------------------------
#### Recherche par auteur:

db.livres.find({ auteur: "Fiodor doestovieski" }).explain("executionStats")

Nombre de document examiné: 2000
Temps d'éxécution: 1 millisecondes
Type d'étape: COLLSCAN

------------------------
#### Recherche par prix:

db.livres.find({ prix: { $gte: 10, $lte: 20 }, note_moyenne: { $gte: 1 } }).explain("executionStats")

Nombre de document examiné: 2000
Temps d'éxécution: 1 millisecondes
Type d'étape: COLLSCAN

------------------------
#### Recherche par genre et langue avec tri par note décroissante:

db.livres.find({ genre: "Roman", langue: "Français" }).sort({ note_moyenne: -1 }).explain("executionStats")

Nombre de document examiné: 2000
Temps d'éxécution: 1 millisecondes
Type d'étape: SORT