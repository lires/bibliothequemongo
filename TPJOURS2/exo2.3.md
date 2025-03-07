### Exercice 2.3

#### 1.  Utilisez $geoWithin pour trouver tous les utilisateurs à l'intérieur d'une zone définie par un polygone (par exemple, un quartier de Paris).

db.utilisateurs.find({
    "adresse.localisation": {
        $geoWithin: {
            $geometry: {
                "type": "Polygon",
                "coordinates": [
                    [
                        [2.3575, 48.8570],
                        [2.3693, 48.8570],
                        [2.3693, 48.8490],
                        [2.3575, 48.8490],
                        [2.3575, 48.8570]
                    ]
                ]
            }
        }
    }
})

#### 2.  Trouvez tous les utilisateurs qui se trouvent dans la zone de service d'une bibliothèque spécifique

db.utilisateurs.find({
    "adresse.localisation": {
        $geoWithin: {
            $geometry: {
                "type": "Polygon",
                "coordinates": [
                    [
                        [2.4315, 48.7813],
                        [2.4550, 48.7813],
                        [2.4550, 48.7585],
                        [2.4315, 48.7585],
                        [2.4315, 48.7813]
                    ]
                ]
            }
        }
    }
})


#### 3.  Créez une collection rues avec au moins une rue représentée comme un LineString GeoJSON, puis utilisez $geoIntersects pour trouver les bibliothèques dont la zone de service intersecte cette rue.


db.rues.insertOne({
  "nom": "rue de la rose",
  "loc": {
    "type": "LineString",
    "coordinates": [
      [2.350, 48.4566],
      [2.360, 48.4666]
    ]
  }
});

db.rues.createIndex({ "loc": "2dsphere" });

db.bibliotheques.find({
  "loc": {
    $geoIntersects: {
      $geometry: {
        "type": "LineString",
        "coordinates": [
          [2.350, 48.4566],
          [2.360, 48.4666]
        ]
      }
    }
  }
});
