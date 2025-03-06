### Exercice 2.1


#### 1. Modifiez le schéma de vos utilisateurs pour inclure des coordonnées géographiques dans leur adresse. Utilisez le format GeoJSON Point 

db.utilisateurs.insertMany([
  {
    nom: "Badel hachik",
    email: "Badel.hachik@kyc.com",
    adresse: {
      rue: "12 rue de la république",
      ville: "Paris",
      code_postal: "92000",
      localisation: {
        type: "Point",
        coordinates: [4.8357, 45.7640]
      }
    }
  },
  {
    nom: "Jayden boudellet",
    email: "Jayden.boudellet@jenaimarre.com",
    adresse: {
      rue: "34 rue edward",
      ville: "Lyon",
      code_postal: "69003",
      localisation: {
        type: "Point",
        coordinates: [5.3698, 43.2965]
      }
    }
  },
  {
    nom: "Alice barnda",
    email: "alice.barnda@kyx.com",
    adresse: {
      rue: "2 rue fable",
      ville: "Marseille",
      code_postal: "13001",
      localisation: {
        type: "Point",
        coordinates: [2.3522, 48.8566]
      }
    }
  },
  {
    nom: "sacripant edxx",
    email: "sacripant.edxx@kyc.com",
    adresse: {
      rue: "101 Pine taimort",
      ville: "Toulouse",
      code_postal: "31000",
      localisation: {
        type: "Point",
        coordinates: [1.4440, 43.6047]
      }
    }
  },
  {
    nom: "Rachid Brown",
    email: "Rachid.brown@kyc.com",
    adresse: {
      rue: "202 route de Rada",
      ville: "Nice",
      code_postal: "06000",
      localisation: {
        type: "Point",
        coordinates: [7.2620, 43.7100]
      }
    }
  }
])

#### 2. Créez une nouvelle collection bibliotheques avec au moins 3 bibliothèques dans différentes villes. Chaque document doit contenir 

db.bibliotheques.insertMany([
    {
        "nom": "Bibliothèque de Paris",
        "adresse": {
            "rue": "10 Rue de Rivoli",
            "ville": "Paris",
            "code_postal": "75004",
            "localisation": {
                "type": "Point",
                "coordinates": [2.3522, 48.8566]
            }
        },
        "zone_service": {
            "type": "Polygon",
            "coordinates": [[
                [2.406696848513815, 48.85434641805345],
                [5.285636434673658, 43.40439542765628],
                [4.912407287429349, 45.69607795423387],
                [2.406696848513815, 48.85434641805345]
            ]]
        }
    },
    {
        "nom": "Bibliothèque de Lyon",
        "adresse": {
            "rue": "25 Quai Jean Moulin",
            "ville": "Lyon",
            "code_postal": "69002",
            "localisation": {
                "type": "Point",
                "coordinates": [4.8357, 45.7640]
            }
        },
        "zone_service": {
            "type": "Polygon",
            "coordinates": [[
                [2.406696848513815, 48.85434641805345],
                [5.285636434673658, 43.40439542765628],
                [4.912407287429349, 45.69607795423387],
                [2.406696848513815, 48.85434641805345]
            ]]
        }
    },
    {
        "nom": "Bibliothèque de Marseille",
        "adresse": {
            "rue": "58 Rue de la République",
            "ville": "Marseille",
            "code_postal": "13002",
            "localisation": {
                "type": "Point",
                "coordinates": [5.3764, 43.2965]
            }
        },
        "zone_service": {
            "type": "Polygon",
            "coordinates": [[
                [2.406696848513815, 48.85434641805345],
                [5.285636434673658, 43.40439542765628],
                [4.912407287429349, 45.69607795423387],
                [2.406696848513815, 48.85434641805345]
            ]]
        }
    }
])
