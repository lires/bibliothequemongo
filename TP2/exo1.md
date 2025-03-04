### J'ai utilise insertMany pour pouvoir ajouter plusieurs objets en même temps


db.produits.insertMany([
  {
    "nom": "Écran Gaming 32 pouces 240Hz",
    "description": "Moniteur gaming avec fréquence ultra rapide de 240Hz et dalle IPS.",
    "prix": 599.99,
    "stock": 15,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "32 pouces",
      "résolution": "2560x1440 (QHD)",
      "tauxRafraîchissement": "240Hz",
      "tempsRéponse": "1ms",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Kevin", "note": 5, "commentaire": "Parfait pour les FPS compétitifs !" }
    ],
    "tags": ["écran", "gaming", "240Hz", "QHD"]
  },
  {
    "nom": "Écran 27 pouces 4K UHD",
    "description": "Moniteur 4K avec HDR pour une qualité d’image exceptionnelle.",
    "prix": 449.99,
    "stock": 25,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "27 pouces",
      "résolution": "3840x2160 (4K UHD)",
      "tauxRafraîchissement": "60Hz",
      "tempsRéponse": "5ms",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Sophie", "note": 5, "commentaire": "Idéal pour le montage vidéo !" }
    ],
    "tags": ["écran", "4K", "HDR", "création"]
  },
  {
    "nom": "Écran Courbé 34 pouces Ultrawide",
    "description": "Écran courbé pour une immersion totale et une meilleure productivité.",
    "prix": 529.99,
    "stock": 18,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "34 pouces",
      "résolution": "3440x1440 (UWQHD)",
      "tauxRafraîchissement": "144Hz",
      "tempsRéponse": "4ms",
      "technologie": "VA"
    },
    "commentaires": [
      { "utilisateur": "Lucas", "note": 4, "commentaire": "Bon pour le travail et le gaming." }
    ],
    "tags": ["écran", "ultrawide", "courbé", "144Hz"]
  },
  {
    "nom": "Écran Portable 15.6 pouces",
    "description": "Écran secondaire portable idéal pour les déplacements.",
    "prix": 199.99,
    "stock": 30,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "15.6 pouces",
      "résolution": "1920x1080 (Full HD)",
      "tauxRafraîchissement": "60Hz",
      "tempsRéponse": "6ms",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Manon", "note": 5, "commentaire": "Super pratique en déplacement !" }
    ],
    "tags": ["écran", "portable", "Full HD"]
  },
  {
    "nom": "Écran 24 pouces 144Hz",
    "description": "Écran fluide et rapide, parfait pour les gamers.",
    "prix": 189.99,
    "stock": 40,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "24 pouces",
      "résolution": "1920x1080 (Full HD)",
      "tauxRafraîchissement": "144Hz",
      "tempsRéponse": "1ms",
      "technologie": "TN"
    },
    "commentaires": [
      { "utilisateur": "Thomas", "note": 5, "commentaire": "Super réactif pour les FPS." }
    ],
    "tags": ["écran", "gaming", "144Hz"]
  },
  {
    "nom": "Écran Tactile 21.5 pouces",
    "description": "Moniteur tactile Full HD pour une meilleure interactivité.",
    "prix": 299.99,
    "stock": 22,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "21.5 pouces",
      "résolution": "1920x1080 (Full HD)",
      "tactile": "Oui",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Emma", "note": 4, "commentaire": "Très pratique pour les présentations." }
    ],
    "tags": ["écran", "tactile", "Full HD"]
  },
  {
    "nom": "Écran 49 pouces Super Ultrawide",
    "description": "Écran ultra-large 49 pouces pour une immersion totale.",
    "prix": 999.99,
    "stock": 10,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "49 pouces",
      "résolution": "5120x1440 (DQHD)",
      "tauxRafraîchissement": "120Hz",
      "tempsRéponse": "4ms",
      "technologie": "VA"
    },
    "commentaires": [
      { "utilisateur": "Julien", "note": 5, "commentaire": "Incroyable pour le multitâche et le gaming !" }
    ],
    "tags": ["écran", "ultrawide", "49 pouces"]
  },
  {
    "nom": "Écran Professionnel 32 pouces 5K",
    "description": "Écran haute précision pour graphistes et créateurs.",
    "prix": 1299.99,
    "stock": 5,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "32 pouces",
      "résolution": "5120x2880 (5K)",
      "tauxRafraîchissement": "60Hz",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Marc", "note": 5, "commentaire": "Parfait pour la retouche photo et le design." }
    ],
    "tags": ["écran", "5K", "création"]
  },
  {
    "nom": "Écran Budget 22 pouces",
    "description": "Moniteur simple et abordable pour la bureautique.",
    "prix": 99.99,
    "stock": 50,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "22 pouces",
      "résolution": "1920x1080 (Full HD)",
      "tauxRafraîchissement": "60Hz",
      "technologie": "TN"
    },
    "commentaires": [
      { "utilisateur": "David", "note": 4, "commentaire": "Très bon rapport qualité-prix." }
    ],
    "tags": ["écran", "budget", "Full HD"]
  },
  {
    "nom": "Écran 27 pouces HDR10",
    "description": "Écran avec support HDR10 pour des couleurs plus vives.",
    "prix": 349.99,
    "stock": 20,
    "categorie": "Informatique",
    "sousCategorie": "Écrans",
    "caracteristiquesTechniques": {
      "taille": "27 pouces",
      "résolution": "2560x1440 (QHD)",
      "HDR": "HDR10",
      "technologie": "IPS"
    },
    "commentaires": [
      { "utilisateur": "Sophie", "note": 5, "commentaire": "Superbe qualité d’image !" }
    ],
    "tags": ["écran", "HDR", "QHD"]
  }
])
