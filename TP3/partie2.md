### 1. Trouve tous les livres disponibles
db.livres.find({ disponible: true })

### 2. Trouve les livres publiés après les années 2000
db.livres.find({ annee_publication: { $gt: 2000 } })

### 3. Trouve les livres d'un auteur 
db.livres.find({ auteur: "Victor Hugo" })

### 4. Trouve les livres qui ont une note supérieure à 4
db.livres.find({ note_moyenne: { $gt: 4 } })

### 5. Trouve les utilisateurs habitant à paris
db.utilisateurs.find({ "adresse.ville": "Paris" })

### 6. Trouve les livres qui appartiennent à un genre
db.livres.find({ genre: "Fantasy" })

### 7. Trouve les livres qui coute moins que 15€ et qui ont une note supérieure à 4
db.livres.find({ prix: { $lt: 15 }, note_moyenne: { $gt: 4 } })

### 8. Trouve les utilisateurs qui ont prit un livre spécifique 
db.utilisateurs.find({ "livres_empruntes.titre": "Le Petit Prince" })
