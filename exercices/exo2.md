# 1. Est-ce doit stocker de l'information ?

Oui

# 2. Quelles sont les entités en jeu ?

- Entité : Utilisateur
- Entité : Video
- Entité : Commentaire

# 3. Quelles sont les relations ?

Utilisateur - Video (créer)
Utilisateur - Commentaire (laisser)
Video - Commentaire (posséder)

# 4. Quelles sont les cardinalités ?

Utilisateur - Video (créer, 1-n)

1. Combien `Utilisateur` peut `créer` 1 meme `Video` ? Réponse : 1
2. Combien de `Video` peuvent `etre créées` par 1 meme `Utilisateur` ? Réponse :  n

Utilisateur - Commentaire (laisser, 1-n)

1. Combien `Utilisateur` peuvent `laisser` 1 meme `Commentaire` ? Réponse : 1
2. Combien de `Commentaire` peuvent `etre laissés` par 1 meme `Utilisateur` ? Réponse : n

Video - Commentaire (posséder, 1-n)

1. Combien de `Video` peuvent `posséder` 1 meme `Commentaire` ? Réponse : 1
2. Combien de `Commentaire` peuvent `etre possédé` par 1 meme `Video` ? Réponse : n

# 5. Quelles sont les clés primaires et étrangères ?

- Table : Utilisateur
    - id (PK)

- Table : Video
    - id (PK)
    - utilisateur_id (FK)

- Table : Commentaire
    - id (PK)
    - utilisateur_id (FK)
    - video_id (FK)

# 6. Quels sont les attributs ?

- Table : Utilisateur
    - id (PK)
    - pseudo
    - image

- Table : Video
    - id (PK)
    - utilisateur_id (FK)
    - duree
    - titre

- Table : Commentaire
    - id (PK)
    - utilisateur_id (FK)
    - video_id (FK)
    - titre
    - date
    - contenu

