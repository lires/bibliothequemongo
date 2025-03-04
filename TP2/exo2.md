### 1. Récupérer tous les produits d’une catégorie
db.produits.find({ categorie: "Informatique" })

### 2. Trouver les produits dont le prix est entre 50€ et 200€
db.produits.find({ prix: { $gte: 50, $lte: 200 } })

### 3. Lister les produits en stock (stock > 0)
db.produits.find({ stock: { $gt: 0 } })

### 4. Trouver les produits avec au moins 3 avis
db.produits.find({ "commentaires.2": { $exists: true } })
