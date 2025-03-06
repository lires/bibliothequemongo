### Exercice 2.2

#### 1.  Trouvez les 5 utilisateurs les plus proches d'un point donné (par exemple, le centre de Paris) dans un rayon de 5km.

##### Ajout d'un index 2d sphere
db.utilisateurs.createIndex({ "adresse.localisation": "2dsphere" })

db.utilisateurs.aggregate([
    {
        $geoNear: {
            near: {
                type: "Point",
                coordinates: [2.3522, 48.8566]
            },
            distanceField: "distance_km",
            maxDistance: 5000,
            spherical: true
        }
    },
    { 
        $limit: 5
    }
])

#### 2.  Trouvez les bibliothèques les plus proches d'un utilisateur spécifique.

db.bibliotheques.find({
    "adresse.localisation": {
        $near: {
            $geometry: {
                "type": "Point",
                "coordinates": [5.3698, 43.2965]
            },
            $maxDistance: 20000
        }
    }
}).limit(1)

#### 3.   Utilisez l'opérateur $geoNear dans un pipeline d'agrégation pour obtenir les bibliothèques triées par distance et calculer précisément cette distance (en km).

db.bibliotheques.aggregate([
    {
        $geoNear: {
            near: {
                type: "Point",
                coordinates: [5.3698, 43.2965]
            },
            distanceField: "distance_km",
            spherical: true,
            distanceMultiplier: 0.01
        }
    },
])
