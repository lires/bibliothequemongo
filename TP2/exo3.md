### 1. Augmenter le prix de tous les produits d’une catégorie de 5%
db.produits.updateMany(
  { categorie: "Informatique" }, 
  { $mul: { prix: 1.05 } }
)

### 2. Ajouter un champ "promotion" à certains produits
db.produits.updateMany(
  { nom: { $in: ["Laptop Pro 15", "Télévision 4K Ultra HD"] } },
  { $set: { promotion: true } }
)

### 3. Ajouter un nouveau tag à tous les produits d’une catégorie
db.produits.updateMany(
  { categorie: "Audio" }, 
  { $addToSet: { tags: "nouveau" } }
)

### 4. Mettre à jour le stock après une "vente"
db.produits.updateOne(
  { nom: "Smartphone X1" }, 
  { $inc: { stock: -1 } }
)

