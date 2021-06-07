# 1. Est-ce doit stocker de l'information ?

- Oui

# 2. Quelles sont les entités/tables en jeu ?

- Table : clients
- Table : produits
- Table : commandes

# 3. Quelles sont les relations ?

- clients - commandes (commander)
- produits - commandes (inclure)

On ne met pas cette relation : - clients - produits (acheter). car ell eest en doublon

# 4. Quelles sont les cardinalités ?

- clients - commandes (commander, 1-n)

1. combien de `clients` peuvent `commander` 1 meme `commande` ? Réponse : 1
2. combien de `commandes` peuvent `etre commandees` par 1 meme `client` ? Réponse : n

- produits - commandes (inclure, n-n)

1. combien de `produits` peuvent `etre inclus` dans 1 meme `commande` ? Réponse : n
2. combien de `commandes` peuvent `inclure` 1 meme `produit` ? Réponse : n

# 5. Quelles sont les clés primaires et étrangères ?

- Table : clients
    - id (PK)

- Table : produits
    - id (PK)

- Table : commandes
    - id (PK)
    - client_id (FK)

- Table : produits_commandes
    - produit_id (FK)
    - commande_id (FK)

# 6. Quels sont les attributs ?

- Table : clients
    - id (PK)
    - nom
    - telephone
    - adresse

- Table : produits
    - id (PK)
    - nom
    - description
    - prix
    - dimensions

- Table : commandes
    - id (PK)
    - client_id (FK)
    - reference
    - date
    - livre_ou_non

- Table : produits_commandes
    - produit_id (FK)
    - commande_id (FK)
    - quantite

