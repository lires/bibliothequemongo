### Exercice 1.2
Recherche par titre:

db.livres.createIndex({ titre: 1 })
db.livres.find({ titre: "Le petit chaeperon rouge" }).explain("executionStats")

Nombre de document examiné: 0
Temps d'éxécution: 0 millisecondes
Type d'étape: IXSCAN

------------------------
Recherche par auteur:

db.livres.createIndex({ auteur: 1 })
db.livres.find({ auteur: "Fiodor doestovieski" }).explain("executionStats")

Nombre de document examiné: 0
Temps d'éxécution: 0 millisecondes
Type d'étape: IXSCAN

------------------------
Recherche par prix:

db.livres.createIndex({ prix: 1, note_moyenne: 1 })
db.livres.find({ prix: { $gte: 10, $lte: 20 }, note_moyenne: { $gte: 1 } }).explain("executionStats")

Nombre de document examiné: 179
Temps d'éxécution: 2 millisecondes
Type d'étape: IXSCAN

------------------------
Recherche par genre et langue avec tri par note décroissante:

db.livres.createIndex({ genre: 1, langue: 1, note_moyenne: -1 })
db.livres.find({ genre: "Roman", langue: "Français" }).sort({ note_moyenne: -1 }).explain("executionStats")

Nombre de document examiné: 0
Temps d'éxécution: 1 millisecondes
Type d'étape: IXSCAN