### 1. Mettez à jour le titre d'un livre spécifique
db.livres.updateOne(
  { titre: "Le Petit Prince" },
  { $set: { titre: "Le Petit Prince et la petite princessette" } }
)

### 2. Ajoutez un champ à tous les livres avec une valeur par défaut de 5
db.livres.updateMany(
  { stock: { $exists: false } },
  { $set: { stock: 12 } }
)

### 3. Marquez un livre comme indisponible
db.livres.updateOne(
  { titre: "1984" },
  { $set: { disponible: false } }
)

### 4. Ajoutez un nouvel emprunt d'un utilisateur
db.utilisateurs.updateOne(
  { email: "marie.dupont@example.com" },
  { $push: { livres_empruntes: {
      livre_id: ObjectId("65f6a5b8d6e4c3b2a1d4f7ec"),
      titre: "L'Étranger",
      date_emprunt: new Date("2024-03-04"),
      date_retour_prevue: new Date("2024-10-04")
    } }
  }
)

### 5. Changez l'adresse d'un utilisateur
db.utilisateurs.updateOne(
  { email: "thomas.martin@example.com" },
  { $set: { "adresse.ville": "Lyon", "adresse.code_postal": "69000" } }
)

### 6. Ajoutez un nouveau tag à un utilisateur
db.utilisateurs.updateOne(
  { email: "sophie.lemoine@example.com" },
  { $addToSet: { tags: "romance" } }
)

### 7. Mettez à jour la note moyenne d'un livre
db.livres.updateOne(
  { titre: "Les Misérables" },
  { $set: { note_moyenne: 4.9 } }
)
