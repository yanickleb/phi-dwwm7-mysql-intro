Besoin : Faire une plateforme pour que des **gens** puissent **réserver** des **chambres** dans des **hotels**.

# 1. Est-ce doit stocker de l'information ?

Oui

# 2. Quelles sont les entités en jeu ?

Si j'ai une idée d'une entité `Ville` ?

- Est-ce que je veux **stocker** plusieurs caractéristiques propres à la `Ville` ?
1. Oui : Entité
2. Non : pas d'entité

- Entite : Chambre
- Entite : Utilisateur
- Entite : Hotel
- Entite : Reservation

# 3. Quelles sont les relations ?

Hotel - Chambre (contenir)
Reservation - Chambre (bloquer)
Utilisateur - Reservation (faire)

# 4. Quelles sont les cardinalités ?

Hotel - Chambre (contenir, 1-n)

1. Combien de `Hotel` peuvent `contenir` 1 meme `Chambre` ? Réponse : 1
2. Combien de `Chambres` peuvent `etre contenu` dans 1 meme `Hotel` ? Réponse : n

Reservation - Chambre (bloquer, 1-n)

1. Combien de `Reservation` peuvent bloquer 1 meme `Chambre` ? Réponse : 1
2. Combien de `Chambre` peuvent `etre bloquées` par 1 meme `Reservation` ? Réponse : n

Utilisateur - Reservation (faire, 1-n)

1. Combien de `Utilisateur` peuvent `faire` 1 meme `Reservation` ? Réponse : 1
2. Combien de `Reservation` peuvent `etre faite` par 1 meme `Utilisateur` ? Réponse : n

# 5. Quelles sont les clés primaires et étrangères ?

- Entite : Chambre
    - id (PK)
    - hotel_id (FK)
    - reservation_id (FK)

- Entite : Utilisateur
    - id (PK)

- Entite : Hotel
    - id (PK)

- Entite : Reservation
    - id (PK)
    - utilisateur_id (FK)

# 6. Quels sont les attributs ?

- Entite : Chambre
    - id (PK)
    - hotel_id (FK)
    - reservation_id (FK)
    - numero
    - capacite

- Entite : Utilisateur
    - id (PK)
    - nom
    - email
    - telephone

- Entite : Hotel
    - id (PK)
    - adresse
    - ville
    - nom

- Entite : Reservation
    - id (PK)
    - utilisateur_id (FK)
    - numero
    - dateheure_de_debut
    - dateheure_de_fin
