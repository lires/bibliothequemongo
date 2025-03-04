### 1.1 Ajouter 5 livres

db.livres.insertMany([
  {
    titre: "Le Petit Prince",
    auteur: "Antoine de Saint-Exupéry",
    annee_publication: 1943,
    editeur: "Gallimard",
    genre: ["Conte", "Philosophie"],
    nombre_pages: 96,
    langue: "Français",
    disponible: true,
    stock: 3,
    note_moyenne: 4.8,
    description: "Un pilote d'avion, qui s'est écrasé dans le désert du Sahara, rencontre un jeune prince venu d'une autre planète...",
    prix: 7.50,
    isbn: "9782070612758",
    date_ajout: new Date("2023-01-15")
  },
  {
    titre: "1984",
    auteur: "George Orwell",
    annee_publication: 1949,
    editeur: "Secker & Warburg",
    genre: ["Dystopie", "Science-fiction"],
    nombre_pages: 328,
    langue: "Français",
    disponible: true,
    stock: 5,
    note_moyenne: 4.7,
    description: "Un monde totalitaire où Big Brother surveille tout et où la pensée libre est un crime.",
    prix: 9.99,
    isbn: "9780451524935",
    date_ajout: new Date("2023-02-20")
  },
  {
    titre: "Harry Potter à l'école des sorciers",
    auteur: "J.K. Rowling",
    annee_publication: 1997,
    editeur: "Gallimard Jeunesse",
    genre: ["Fantasy", "Aventure"],
    nombre_pages: 320,
    langue: "Français",
    disponible: true,
    stock: 10,
    note_moyenne: 4.9,
    description: "Un jeune garçon découvre qu'il est un sorcier et intègre Poudlard, une école de magie.",
    prix: 12.99,
    isbn: "9782070643028",
    date_ajout: new Date("2023-03-10")
  },
  {
    titre: "Les Misérables",
    auteur: "Victor Hugo",
    annee_publication: 1862,
    editeur: "Pagnerre",
    genre: ["Roman", "Historique"],
    nombre_pages: 1462,
    langue: "Français",
    disponible: false,
    stock: 0,
    note_moyenne: 4.6,
    description: "L'histoire de Jean Valjean, un ancien bagnard en quête de rédemption dans la France du XIXe siècle.",
    prix: 15.00,
    isbn: "9782253004201",
    date_ajout: new Date("2023-04-05")
  },
  {
    titre: "L'Étranger",
    auteur: "Albert Camus",
    annee_publication: 1942,
    editeur: "Gallimard",
    genre: ["Roman", "Philosophie"],
    nombre_pages: 185,
    langue: "Français",
    disponible: true,
    stock: 7,
    note_moyenne: 4.5,
    description: "Meursault, un homme indifférent, est jugé pour un meurtre qu'il a commis sans réelle raison.",
    prix: 8.50,
    isbn: "9782070360024",
    date_ajout: new Date("2023-05-18")
  },
  {
    titre: "Le Seigneur des Anneaux",
    auteur: "J.R.R. Tolkien",
    annee_publication: 1954,
    editeur: "Christian Bourgois",
    genre: ["Fantasy", "Aventure"],
    nombre_pages: 1178,
    langue: "Français",
    disponible: true,
    stock: 4,
    note_moyenne: 4.9,
    description: "Une épopée fantastique où un groupe de héros tente de détruire un anneau maléfique.",
    prix: 25.99,
    isbn: "9782266154112",
    date_ajout: new Date("2023-06-30")
  }
])


### 1.3 Ajouter 3 utilisateurs

db.utilisateurs.insertMany([
  {
    nom: "Dupont",
    prenom: "Marie",
    email: "marie.dupont@example.com",
    age: 28,
    adresse: {
      rue: "123 Avenue des Livres",
      ville: "Lyon",
      code_postal: "69002"
    },
    date_inscription: new Date("2022-12-10"),
    livres_empruntes: [
      {
        livre_id: ObjectId("65f6a5b8d6e4c3b2a1d4f7e9"), // Remplacer par un vrai ID
        titre: "Le Petit Prince",
        date_emprunt: new Date("2023-02-15"),
        date_retour_prevue: new Date("2023-03-15")
      }
    ],
    tags: ["fiction", "histoire"]
  },
  {
    nom: "Martin",
    prenom: "Thomas",
    email: "thomas.martin@example.com",
    age: 35,
    adresse: {
      rue: "45 Rue des Romans",
      ville: "Paris",
      code_postal: "75008"
    },
    date_inscription: new Date("2021-07-22"),
    livres_empruntes: [
      {
        livre_id: ObjectId("65f6a5b8d6e4c3b2a1d4f7ea"), // Remplacer par un vrai ID
        titre: "1984",
        date_emprunt: new Date("2023-06-10"),
        date_retour_prevue: new Date("2023-07-10")
      },
      {
        livre_id: ObjectId("65f6a5b8d6e4c3b2a1d4f7eb"), // Remplacer par un vrai ID
        titre: "Les Misérables",
        date_emprunt: new Date("2023-08-01"),
        date_retour_prevue: new Date("2023-09-01")
      }
    ],
    tags: ["dystopie", "classique"]
  },
  {
    nom: "Lemoine",
    prenom: "Sophie",
    email: "sophie.lemoine@example.com",
    age: 24,
    adresse: {
      rue: "89 Boulevard des Écrivains",
      ville: "Marseille",
      code_postal: "13001"
    },
    date_inscription: new Date("2023-03-05"),
    livres_empruntes: [
      {
        livre_id: ObjectId("65f6a5b8d6e4c3b2a1d4f7ec"), // Remplacer par un vrai ID
        titre: "Harry Potter à l'école des sorciers",
        date_emprunt: new Date("2023-09-20"),
        date_retour_prevue: new Date("2023-10-20")
      }
    ],
    tags: ["fantasy", "magie"]
  }
])
