Vous souhaitez développer une banque en ligne (à l'instar de BNP Paribas) avec les fonctionnalités :

- des **personnes** pourront créer un **compte**
- des **personnes** pourront prendre des **cartes bancaires** associés **leur compte**

# 1. Est-ce doit stocker de l'information ?

Oui

# 2. Quelles sont les entités en jeu ?

Entité : Utilisateur
Entité : Compte
Entité : Carte

Remarque : on crée une entité si l'on doit en gérer **plusieurs**

# 3. Quelles sont les relations ?

- Utilisateur - Compte (créer)
- Compte - Carte (associer)

ATTENTION : la relation Utilisateur-Carte (posséder) a été en doublon

# 4. Quelles sont les cardinalités ?

- Utilisateur - Compte (créer, n-n)

1. Combien de `Utilisateur` peuvent `créer` 1 meme `Compte` ? Reponse : n
2. Combien de `Compte` peuvent `être créé` par 1 meme `Utilisateur` ? Réponse : n

- Compte - Carte (associer, 1-n)

1. Combien de `Compte` peuvent `associer` 1 meme `Carte` ? Réponse : 1
2. Combien de `Carte` peuvent `être associées` à 1 meme `Compte` ? Réponse : n

# 5. Quelles sont les clés primaires et étrangères ?

Table : Utilisateur
    - id (PK)

Table : Compte
    - id (PK)

Table : Carte
    - id (PK)
    - compte_id (FK)

Table : utilisateur_compte
    - utilisateur_id (FK)
    - compte_id (FK)

# 6. Quels sont les attributs ?

Table : Utilisateur
    - id (PK)
    - nom
    - adresse
    - identifiant
    - mot_de_passe

Table : Compte
    - id (PK)
    - iban

Table : Carte
    - id (PK)
    - compte_id (FK)
    - numero
    - code_pin
    - CVC
    - date_expiration
    - type

Table : utilisateur_compte
    - utilisateur_id (FK)
    - compte_id (FK)

