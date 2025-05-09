Titre : Projet Power BI avancé

* Projet très riche avec beaucoup de difficultés surmontées et des problèmes résolus.

Toutes les étapes du présent projet n'ont pas été écrites et détaillées étant données la grande quantité de taches réalisées.

Dans ce projet nous partons de données brutes à un rapport Power BI. Nous partons d'un ensemble de jeux de données brutes enrichis des ventes d'une entreprise fictive nommée Adventure Works pour créer un rapport Power BI de 5 pages que nous allons ensuite publier dans le service Power BI en ligne.

Les étapes de ce projet sont :

1 - connecter les données à Power BI
2 - nettoyer et transformer les données avec Power Query Editor
3 - modéliser les données avec Power BI
4 - créer des mesures
5 - créer des visuels et publier le rapport sur le service Power BI

Concernant la source de données, nous avons trois principaux fichiers : un fichier principal "AdventureWorks Sales.xlsx" qui contient 7 tables : celle des commandes, celle des zones ou territoires de ventes, celle des détails commandes, celle des revendeurs, des dates, des produits, et enfin celle des clients. À côté de ce fichier, nous avons également le fichier "Objectifs_Vente.csv" qui contient les objectifs de ventes et le fichier "Stock.csv" qui contient les stocks par article.

Pour ce qui est des mesures créées, on crée une table dans laquelle on va ranger toutes nos mesures.
Le calcul des mesures est regroupé en deux catégories : KPI de ventes et KPI achat et logistique.

KPI de ventes :

- Chiffre d'affaires
- Marge
- Taux de marge
- Nombre de ventes
- Objectif de ventes
- Panier moyen
- Quantités vendues
- Taux d'atteinte des objectifs

KPI achat et logistique :

- Quantité en stock
- Valeur de stock
- Délai moyen de livraison
- Nombre de livraisons

Le rapport final contient 5 pages, et chaque page montre des résumés stratégiques pour la prise de décision dans l'entreprise. Les différentes pages contiennent :

- Tableau de bord de suivi et de pilotage de la performance
- Suivi des ventes journalières
- Analyse des ventes saisonnières
- Marges détaillées
- Stock détaillé


1 - Connecter les données à Power BI

On charge le fichier "AdventureWorks Sales.xlsx" avec ses 7 tables dans Power BI, puis on clique sur Transformer les données pour ouvrir les tables dans l’Éditeur Power Query.
Avant de commencer à nettoyer les données, on connecte aussi nos autres sources en cliquant sur Nouvelle source. Ces sources sont les fichiers "Objectifs_Vente.csv" et "Stock.csv", chacun contenant une seule table.

2 - Nettoyer et transformer les données avec Power BI

- On renomme la table issue du fichier "Objectifs_Vente.csv" en Objectif de ventes.

- On vérifie les types de données, les valeurs manquantes et les erreurs dans chaque table. Pour nous aider, on active dans Affichage l’option Qualité de la colonne : cela permet de repérer facilement les valeurs manquantes ou les erreurs.

- Toujours dans Affichage, les options Distribution des colonnes et Profil de colonne nous aident aussi pour nettoyer. On remarque par exemple que la couleur noire est la plus représentée, suivie de la couleur rouge.

- On renomme les tables : Customer devient Client, Product devient Produit, Sales Territory devient Territoire de Vente, SalesOrder devient Commandes, Reseller devient Revendeur, Sales devient Ventes.

- On renomme aussi les colonnes : dans la table Client, Customer devient Client, City devient Ville, State-Province devient État-Province, Country-Region devient Pays-Région, et Postal Code devient Code Postal. On fait de même pour les autres tables.

- Dans la table Date, à partir de la colonne Date (format JJ/MM/AAAA), on crée d’autres colonnes : Jour, Mois, Année. On crée aussi Nom du Mois et Nom du Jour à partir de cette colonne.

- On s’arrête là pour les transformations et on clique sur Fermer & Appliquer dans Accueil. Les transformations sont alors appliquées aux données. On pourra toujours revenir dans Power Query si besoin, en cliquant sur Transformer, puis refaire Fermer & Appliquer pour revenir dans Power BI.
Ensuite, on va modéliser le jeu de données dans la Vue de Modèle.

3 - Modéliser les données avec Power BI

Dans la Vue Modèle, on voit que Power BI a déjà détecté les relations entre les tables au moment du chargement. On vérifie que ces relations sont correctes.
À l’avenir, si on ne veut pas que Power BI crée les relations automatiquement, on pourra modifier les options de chargement.
Ici, on ajoute de nouvelles relations : entre Ventes et Date, puis entre Date et Objectif de ventes.
Maintenant, on va créer les mesures nécessaires pour construire nos tableaux de bord.

4 - Créer des mesures

On commence par créer une table pour ranger toutes nos mesures. Pour cela, on clique sur Entrer des données dans Affichage de données (menu Accueil), puis on nomme la table créée Mesures.

Les mesures sont regroupées en deux catégories : KPI de ventes et KPI achat et logistique.

On commence par calculer les mesures pour les KPI de ventes :

KPI de ventes :

- Chiffre d’Affaires : somme des montants avec CALCULATE
- Marge : différence entre montant de vente et prix de revient total
- Taux de marge : marge ÷ prix de revient
- On change le format : Pourcentage pour le taux de marge, Nombre décimal pour les deux autres. On fera pareil pour les prochaines mesures.
- Nombre de ventes : avec DISTINCTCOUNT
- Objectif de ventes
- Panier moyen : chiffre d’affaires ÷ nombre de ventes
- Quantités vendues
- Taux d’atteinte des objectifs

KPI achat et logistique :

- Quantité en stock
- Valeur de stock
- Délai moyen de livraison
- Nombre de livraisons

5 - Construction des pages du rapport

Le rapport contient 5 pages au total.

Première page : Accueil

- On insère une zone de texte pour le titre, menu Accueil --> Zone de texte.
- On met le titre en bleu, on le centre, on augmente la police à 20, on met en gras.
- On grise l’arrière-plan du titre (Effet --> Arrière-plan --> Couleur).
- On insère le logo Adventure Works (menu Insérer).
- On utilise le visuel Carte pour insérer le chiffre d’affaires (ce visuel prend un seul champ, un indicateur clé).
- Dans Mise en forme du visuel : on masque l’étiquette, on met la légende en gras, police 42 ; dans Général, on active le titre, on le saisit, on le centre, on le met en gras, on grise l’arrière-plan.
- On active la bordure visuelle et on met un arrondi de 10.
- On copie ce visuel quatre fois.
- Dans chaque copie, on remplace le chiffre d’affaires par les autres KPI de ventes.
- On ajuste les largeurs des visuels (250 dans Général --> Propriété), puis on les aligne (Format --> Aligner --> Distribuer horizontalement).
- Ensuite, on ajoute des courbes de croissance sur les cartes :
- On choisit un graphique en aires, on met la date (par mois) en abscisse et le chiffre d’affaires en ordonnée.
- On enlève le titre, les valeurs des axes, et le titre général ; on superpose sur la carte ; on met la transparence à 100 % (Effets), on prend une ligne bleu clair.

On crée aussi :

- Un histogramme groupé : objectifs de ventes et chiffre d’affaires (ordonnée), date (abscisse, année).
- On enlève les titres des axes, on met les valeurs au-dessus des barres (étiquettes de données, en noir et gras).
- On centre la légende, on la met en noir et gras, on centre le titre général, on arrondit les bordures à 10.
- Un graphique à barres empilées : chiffre d’affaires par revendeur, avec les mêmes ajustements.
- Un diagramme en anneau : marge par catégorie de produit, on copie la mise en forme, on met les légendes en noir, au centre haut.

Ensuite, on passe aux autres pages :

- Page 2 : suivi des ventes journalières, on y ajoute plusieurs segments.
- Page 3 : analyse des ventes saisonnières.
- Page 4 : marge détaillée (informations non visibles ---> affichées en infobulles).
- Page 5 : stock détaillé.
