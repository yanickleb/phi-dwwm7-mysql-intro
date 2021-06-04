Vous souhaitez développer une plateforme de partage d'**applications** (à l'instar de AppStore) avec les fonctionnalités suivantes :
- des **developpeurs** pourront **publier** leurs **applications**
- des **utilisateurs** pourront **télécharger** l'**application** sur leurs différents **appareils**

# 1. Est-ce doit stocker de l'information ?

Oui

# 2. Quelles sont les entités en jeu ?

Entité : Développeur
Entité : Application
Entité : Utilisateur
Entité : Appareil

# 3. Quelles sont les relations ?

Développeur - Application (publier)
Utilisateur - Application (telecharger)
Appareil - Application (installer)
Appareil - Application (etre compatible)

# 4. Quelles sont les cardinalités ?

Développeur - Application (publier, 1-n)

1. Combien de `Développeur` peuvent `publier` 1 meme `Application` ? Réponse 1
2. Combien de `Application` peuvent `etre publie` par 1 meme `Développeur` ? Réponse n

Utilisateur - Application (telecharger, n-n)

1. Combien de `Utilisateur` peuvent `telecharger` 1 meme `Application` ? Réponse n
2. Combien de `Application` peuvent `etre telechargee` par 1 meme `Utilisateur` ? Réponse n

Appareil - Application (installer, n-n)

1. Combien de `Appareil` peuvent `installer` 1 meme `Application` ? Réponse n
2. Combien de `Application` peuvent `etre installee` par 1 meme `Appareil` ? Réponse n

Appareil - Application (etre compatible, n-n)

1. Combien de `Appareil` peuvent `etre compatible` avec 1 meme `Application` ? Réponse n
2. Combien de `Application` peuvent `etre etre compatible` avec 1 meme `Appareil` ? Réponse n

# 5. Quelles sont les clés primaires et étrangères ?

Table : Développeur
    - id (PK)

Table : Application
    - id (PK)
    - developpeur_id (FK)
    
Table : Utilisateur
    - id (PK)

Table : Appareil
    - id (PK)

Table : Telechargement
    - utilisateur_id (FK)
    - application_id (FK)

Table : Installation
    - appareil_id (FK)
    - application_id (FK)

Table : Compatibilite
    - appareil_id (FK)
    - application_id (FK)

# 6. Quels sont les attributs ?

Table : Développeur
    - id (PK)
    - email
    - enseigne
    - SIRET

Table : Application
    - id (PK)
    - developpeur_id (FK)
    - titre
    - description
    - prix
    
Table : Utilisateur
    - id (PK)
    - email

Table : Appareil
    - id (PK)
    - modele
    - systeme_d_exploitation

Table : Telechargement
    - utilisateur_id (FK)
    - application_id (FK)

Table : Installation
    - appareil_id (FK)
    - application_id (FK)

Table : Compatibilite
    - appareil_id (FK)
    - application_id (FK)