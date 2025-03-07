### Exercice 2.4

#### 1.  Créez une collection livraisons pour suivre les livraisons de livres, avec :

db.livraisons.createIndex({ "depart_du_livreur": "2dsphere" });
db.livraisons.createIndex({ "arrivee_du_livreur": "2dsphere" });
db.livraisons.createIndex({ "position_du_livreur": "2dsphere" });
db.livraisons.createIndex({ "itineraire_du_livreur": "2dsphere" });

#### 2.  Implémentez une fonction pour mettre à jour la position d'une livraison
function updateLivreurPosition(deliveryId, newLon, newLat) {
  db.livraisons.updateOne(
    { _id: deliveryId },
    { $set: { position_du_livreur: { type: "Point", coordinates: [newLon, newLat] } } }
  );
}

#### 3.  Créez une requête pour trouver toutes les livraisons en cours dans un rayon de 1km autour d'un point donné.
db.livraisons.find({
  statut: "en cours",
  position_du_livreur: {
    $near: {
      $geometry: {
        type: "Point",
        coordinates: [4.8397, 45.7640]
      },
      $maxDistance: 1000
    }
  }
});