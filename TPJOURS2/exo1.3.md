### Exercice 1.3
#### Création d'un index type text:

db.livres.createIndex({ titre: "text", description: "text" })
db.livres.find({ $text: { $recherche: "rouge" } }).explain("executionStats")

Nombre de document examiné: 0
Temps d'éxécution: 1 millisecondes
Type d'étape: TEXT_MATCH


#### Crée une nouvelle collection puis ajouter du contenue:

db.sessions_utilisateurs.insertMany([
  {
    userId: 1,
    derniereActivite: new Date(),
    sessionData: { page: "accueil", device: "mobile" }
  },
  {
    userId: 2,
    derniereActivite: new Date(),
    sessionData: { page: "dashboard", device: "desktop" }
  },
  {
    userId: 3,
    derniereActivite: new Date(),
    sessionData: { page: "profile", device: "tablet" }
  },
  {
    userId: 4,
    derniereActivite: new Date(),
    sessionData: { page: "parametre", device: "mobile" }
  },
  {
    userId: 5,
    derniereActivite: new Date(),
    sessionData: { page: "accueil", device: "desktop" }
  },
  {
    userId: 6,
    derniereActivite: new Date(),
    sessionData: { page: "recherche", device: "tablet" }
  },
  {
    userId: 7,
    derniereActivite: new Date(),
    sessionData: { page: "accueil", device: "desktop" }
  },
  {
    userId: 8,
    derniereActivite: new Date(),
    sessionData: { page: "profile", device: "mobile" }
  },
  {
    userId: 9,
    derniereActivite: new Date(),
    sessionData: { page: "parametre", device: "tablet" }
  },
  {
    userId: 10,
    derniereActivite: new Date(),
    sessionData: { page: "dashboard", device: "mobile" }
  }
])


#### Créer un TTL pour supprimer après 30 minutes d'inactivité:

db.sessions_utilisateurs.createIndex(
  { "derniereActivite": 1 },
  { expireAfterSeconds: 1800 }
)
