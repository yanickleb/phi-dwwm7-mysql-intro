# Requêtes avec FROM

### Selectionner toutes les colonnes de la table categories

```sql
SELECT * FROM exo1_categories;
```

### Selectionner toutes les colonnes de la table utilisateur

```sql
SELECT * FROM exo1_users;
```

### Selectionner toutes les references des commandes

```sql
SELECT reference FROM exo1_orders;
```

### Selectionner toutes les dates des commandes

```sql
SELECT created_at FROM exo1_orders;
```

### Selectionner toutes les quantites des commandes

```sql
SELECT quantity FROM exo1_order_details;
```

# Requêtes avec WHERE

### Quel est le prix du produit 4 ?

```sql
SELECT price FROM exo1_products WHERE id = 4;
```

### Quel est le prenom de l'utilisateur qui a l'adresse email leo.part@gmail.com ?

```sql
SELECT firstname FROM exo1_users WHERE email = 'leo.part@gmail.com';
```

### Quel est le numero de l'utilisateur qui a passé la commande de reference 94809503 ?

```sql
SELECT user_id FROM exo1_orders WHERE reference = '94809503';
```

### A quelle date s'est faite la commande de reference 39820342 ?

```sql
SELECT created_at FROM exo1_orders WHERE reference = '39820342';
```

# Requêtes avec GROUP BY

### Quel est le nombre de commandes par numero d'utilisateur ?

```sql
SELECT user_id, COUNT(id) AS nombre_de_commandes FROM exo1_orders GROUP BY user_id
```

### Quel est la quantite totale commandée par numero de commande ?

```sql
SELECT order_id AS id_de_commande, SUM(quantity) AS quantite_totale FROM exo1_order_details GROUP BY order_id;
```

### Quel est la quantite totale commandée par numero de produit ?

```sql
SELECT product_id, SUM(quantity) AS quantite_totale FROM exo1_order_details GROUP BY product_id;
```

### Quel est le nombre de commandes par numero de produit ?

```sql
SELECT product_id, COUNT(order_id) FROM exo1_order_details GROUP BY product_id;
```

### Quel est le nombre de produits par numero de commande ?

```sql
SELECT order_id, COUNT(product_id) FROM exo1_order_details GROUP BY order_id;
```

# Requêtes avec HAVING

### Quels sont les clients ayant passé 2 commandes ?

```sql
SELECT user_id FROM exo1_orders GROUP BY user_id HAVING COUNT(id) = 2;
```

### Quelles sont les commandes ayant 3 produits différents ?

```sql
SELECT order_id FROM exo1_order_details GROUP BY order_id HAVING COUNT(product_id) = 3;
```

### Quelles sont les commandes ayant 6 articles à expédier ?

```sql
SELECT order_id FROM exo1_order_details GROUP BY order_id HAVING SUM(quantity) = 6;
```

# Requêtes avec ORDER BY, LIMIT

## Quelle est la commande la plus récente ?

```sql
SELECT * FROM exo1_orders ORDER BY created_at DESC LIMIT 1;
```

### Quelle est la commande la plus anciennce ?

```sql
SELECT * FROM exo1_orders ORDER BY created_at ASC LIMIT 1;
```

### Quel est le nom des 3 produits qui coutent le plus chers ?

```sql
SELECT name FROM exo1_products ORDER BY price DESC LIMIT 3;
```

# Requêtes avec JOIN

### Quelles sont toutes les informations des utilisateurs et des commandes ?

```sql
SELECT * FROM 
exo1_users u LEFT OUTER JOIN exo1_orders o
ON o.user_id = u.id;
```
