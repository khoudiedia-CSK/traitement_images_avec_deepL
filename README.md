# Traitement_images_avec_deep_Learnig(CNN)
📝 Contexte du projet 
La reconnaissance faciale est aujourd’hui au cœur de nombreuses applications modernes : sécurité, biométrie, réseaux sociaux, santé, ou encore commerce. Toutefois, reconnaître un visage en conditions réelles reste un défi de taille, en raison des variations d’éclairage, de pose, d'expression, d'âge ou encore de qualité d’image.

Dans ce projet, nous explorons l’utilisation de techniques de deep learning pour aborder le problème de la reconnaissance faciale à partir du jeu de données Labeled Faces in the Wild (LFW). Ce dataset, devenu un standard dans la recherche, propose plus de 13 000 images de visages collectées sur Internet, et annotées avec les noms des personnes photographiées.

Les images ont été détectées à l’aide du détecteur de visages de Viola-Jones, et présentent des conditions variées et non contrôlées — ce qui reflète les difficultés d’une application en environnement réel. Le dataset comporte 1 680 personnes ayant au moins deux images différentes, ce qui le rend particulièrement adapté à l’entraînement de modèles de reconnaissance de visages à l’aide de réseaux de neurones convolutifs (CNN).

Notre objectif dans ce projet est de :

Prétraiter et organiser les images du dataset,

Entraîner un modèle de classification (ou de vérification) de visages,

Évaluer ses performances sur un ensemble de test non vu,

Étudier les limites et axes d’amélioration d’un tel système.

Résumé des essais réalisés
Premier test : CNN simple

Modèle basique avec 2 couches convolutionnelles, 1 couche dense finale.

Images redimensionnées à 64x64 pixels.

Résultat : environ 15 % de précision sur le test.

Limites : modèle trop simple, peu d’images par classe, pas d’augmentation des données, taille d’image faible.

Deuxième test : CNN amélioré + augmentation de données

Ajout d’une couche convolutionnelle supplémentaire, dropout pour éviter le sur-apprentissage.

Augmentation de données (rotation, zoom, translation, flip).

Seules les personnes avec au moins 3 images ont été conservées.

Résultat : environ 21 % de précision.

Amélioration notable, mais encore insuffisant pour une bonne reconnaissance faciale.

Troisième test : transfert learning avec MobileNetV2 pré-entraîné

Images redimensionnées à 160x160 pixels pour correspondre à l’entrée du modèle MobileNetV2.

Filtrage plus strict : minimum 15 images par personne pour un meilleur apprentissage.

Couche de base gelée, ajout d’un classifieur personnalisé avec dropout.

Résultat : environ 54 % de précision.

Conclusion : le transfert learning apporte un vrai gain en performance grâce à l’utilisation de représentations visuelles déjà apprises sur un large corpus d’images.

Points clés à retenir
Qualité des données : avoir suffisamment d’exemples par personne est crucial.

Augmentation des données : nécessaire pour améliorer la robustesse du modèle.

Taille d’image : plus grande, plus d’informations et meilleures performances.

Transfert learning : méthode efficace pour exploiter des modèles pré-entraînés sur de larges bases et les adapter à des tâches spécifiques.
