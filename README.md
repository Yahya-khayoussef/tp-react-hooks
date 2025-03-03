# TP React Hooks - Application de Gestion de Produits

Ce TP a pour objectif de mettre en pratique l'utilisation des Hooks React (useState, useEffect, useContext) ainsi que la création de Hooks personnalisés.

## Installation et configuration initiale

1. Cloner le dépôt :
```bash
git clone https://github.com/pr-daaif/tp-react-hooks.git
cd tp-react-hooks
```

2. Créer votre propre dépôt sur Github et changer le remote :
```bash
# Supprimer le remote origine
git remote remove origin

# Ajouter votre nouveau remote
git remote add origin https://github.com/[votre-username]/tp-react-hooks.git

# Premier push
git push -u origin main
```

3. Installer les dépendances :
```bash
npm install
```

4. Lancer l'application :
```bash
npm start
```

## Instructions pour le TP

Pour chaque exercice :
1. Lisez attentivement l'énoncé
2. Implémentez la solution
3. Testez votre implémentation (pensez à faire des copies d'écran)
4. Mettez à jour la section correspondante dans ce README avec :
   - Une brève explication de votre solution
   - Des captures d'écran montrant le fonctionnement
   - Les difficultés rencontrées et comment vous les avez résolues
5. Commitez vos changements avec un message descriptif

### Exercice 1 : État et Effets 
#### Objectif : Implémenter une recherche en temps réel

- [ ] 1.1 Modifier le composant ProductSearch pour utiliser la recherche
- [ ] 1.2 Implémenter le debounce sur la recherche
- [ ] 1.3 Documenter votre solution ici

_Votre réponse pour l'exercice 1 :_
```
1.1 Modifier le composant ProductSearch pour utiliser la recherche : J'ai modifié le composant ProductSearch pour qu'il puisse gérer la recherche en temps réel. Lorsque l'utilisateur tape dans le champ de recherche, l'état est mis à jour avec le terme de recherche. Une fonction de recherche peut ensuite être appelée.

1.2 Implémenter le debounce sur la recherche : J'ai ajouté un hook personnalisé useDebounce pour retarder l'exécution de la recherche après un délai de 500ms. Cela permet d'éviter d'effectuer des recherches inutiles à chaque frappe. Ce hook attend que l'utilisateur ait cessé de taper pendant 500ms avant de déclencher la recherche.

1.3 Documenter votre solution : J'ai utilisé un hook personnalisé pour gérer le debounce, ce qui a permis d'améliorer les performances en limitant le nombre de recherches envoyées au serveur.

Difficultés rencontrées : L'implémentation du debounce demandait de comprendre comment fonctionnent les effets et les délais dans React, mais après avoir correctement utilisé useEffect et setTimeout, la fonctionnalité a été mise en place.
```

### Exercice 2 : Context et Internationalisation
#### Objectif : Gérer les préférences de langue

- [ ] 2.1 Créer le LanguageContext
- [ ] 2.2 Ajouter le sélecteur de langue
- [ ] 2.3 Documenter votre solution ici

_Votre réponse pour l'exercice 2 :_
```
2.1 Créer le LanguageContext : J'ai créé un LanguageContext pour stocker et fournir les préférences de langue à travers l'application. Cela permet de gérer la sélection de la langue via un sélecteur.

2.2 Ajouter le sélecteur de langue : J'ai ajouté un sélecteur de langue dans le composant principal de l'application. Ce sélecteur permet à l'utilisateur de choisir une langue parmi celles disponibles (par exemple : français, anglais). Le contexte de langue est mis à jour dynamiquement en fonction de la sélection.

2.3 Documenter votre solution : Le LanguageContext a été créé avec useContext et un fournisseur de contexte pour que tous les composants enfants puissent accéder à la langue sélectionnée.

Difficultés rencontrées : La difficulté principale était de bien comprendre comment transmettre les valeurs du contexte à différents composants.
```

### Exercice 3 : Hooks Personnalisés
#### Objectif : Créer des hooks réutilisables

- [ ] 3.1 Créer le hook useDebounce
- [ ] 3.2 Créer le hook useLocalStorage
- [ ] 3.3 Documenter votre solution ici

_Votre réponse pour l'exercice 3 :_
```
3.1 Créer le hook useDebounce : J'ai créé un hook useDebounce qui prend une valeur et un délai en paramètre, et qui renvoie cette valeur après le délai spécifié. Cela permet de retarder l'exécution de fonctions, comme la recherche.

3.2 Créer le hook useLocalStorage : J'ai également créé un hook useLocalStorage qui permet de lire et d'écrire des données dans le localStorage du navigateur. Ce hook simplifie la gestion des données persistantes dans l'application.

3.3 Documenter votre solution : Les hooks créés (useDebounce et useLocalStorage) sont réutilisables dans l'application pour différentes fonctionnalités, rendant le code plus propre et plus modulaire.

Difficultés rencontrées : Bien gérer l'état avec localStorage et synchroniser les données entre le localStorage et l'état React demandait un peu d'attention.
```

### Exercice 4 : Gestion Asynchrone et Pagination
#### Objectif : Gérer le chargement et la pagination

- [ ] 4.1 Ajouter le bouton de rechargement
- [ ] 4.2 Implémenter la pagination
- [ ] 4.3 Documenter votre solution ici

_Votre réponse pour l'exercice 4 :_
```
4.1 Ajouter le bouton de rechargement : J'ai ajouté un bouton qui permet de recharger manuellement les produits affichés. En cliquant dessus, une nouvelle requête est envoyée pour obtenir les données actualisées.

4.2 Implémenter la pagination : J'ai implémenté la pagination pour diviser les résultats en plusieurs pages. Les utilisateurs peuvent naviguer entre les pages pour afficher plus de produits, avec la possibilité de charger les données de manière asynchrone.

4.3 Documenter votre solution : Le rechargement manuel et la pagination ont été implémentés pour améliorer l'expérience utilisateur et limiter la quantité de données chargées à la fois.

Difficultés rencontrées : La gestion des états de chargement asynchrone et la gestion de la pagination étaient des défis, mais en utilisant useEffect et en contrôlant les états de chargement, ces fonctionnalités ont été correctement implémentées.
```