### 1. Listez tous les livres triés par note moyenne
db.livres.find().sort({ note_moyenne: -1 });

### 2. Trouvez les 3 livres les plus anciens
db.livres.find().sort({ annee_publication: 1 }).limit(3);

### 3. Comptez le nombre de livres par auteur
db.livres.aggregate([
  { $group: { _id: "$auteur", nombre_livres: { $sum: 1 } } }
]);

### 4. Affichez uniquement le titre, l'auteur et la note moyenne des livres
db.livres.find({}, { _id: 0, titre: 1, auteur: 1, note_moyenne: 1 });

### 5. Trouvez les utilisateurs qui ont emprunté plus d'un livre
db.utilisateurs.find({ "livres_empruntes.1": { $exists: true } });

### 6. Recherchez les livres dont le titre contient un mot spécifique
db.livres.find({ titre: { $regex: "magie", $options: "i" } });

### 7. Trouvez les livres ou le prix est < 10€ > 20€
db.livres.find({ prix: { $gte: 10, $lte: 20 } });