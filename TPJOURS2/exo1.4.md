### Exercice 1.3
#### Création d'un index pour requete couverte

db.livres.createIndex({ titre: 1, ISBN: 1 })
db.livres.find({ titre: "MongoDB Basics" }, { ISBN: 1 }).explain("executionStats")

####  Créez un index unique sur le champ ISBN des livres et testez son comportement en essayant d'insérer un document avec un ISBN dupliqué.

db.livres.createIndex({ ISBN: 1 }, { unique: true })

#### Créez un index partiel qui n'indexe que les livres disponibles

db.livres.createIndex(
  { titre: 1 },
  { 
    partialFilterExpression: { disponible: true },
    name: "titre_disponible_1"
  }
)

