### 1. Supprimez un livre spécifique par son titre
db.livres.deleteOne({ titre: "1929" });

### 2. Supprimez tous les livres d'un auteur spécifique
db.livres.deleteMany({ auteur: "Ali vadintaba" });

### 3. Supprimez un utilisateur par son email
db.utilisateurs.deleteOne({ email: "marie.dupont@example.com" });
