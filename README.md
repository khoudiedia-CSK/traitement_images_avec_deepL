# Traitement d'Images avec Deep Learning (CNN)

## 📝 Contexte du projet

La reconnaissance faciale est aujourd’hui au cœur de nombreuses applications modernes : sécurité, biométrie, réseaux sociaux, santé, ou encore commerce. Toutefois, reconnaître un visage en conditions réelles reste un défi majeur, en raison des variations d’éclairage, de pose, d'expression, d'âge ou encore de qualité d’image.

Dans ce projet, nous explorons l’utilisation de techniques de **deep learning** pour aborder le problème de la reconnaissance faciale à partir du jeu de données **Labeled Faces in the Wild (LFW)**. Ce dataset, devenu un standard dans la recherche, propose plus de 13 000 images de visages collectées sur Internet, annotées avec les noms des personnes photographiées.

Les images ont été détectées à l’aide du détecteur de visages de Viola-Jones, et présentent des conditions variées et non contrôlées — reflétant ainsi les difficultés d’une application en environnement réel. Le dataset comporte **1 680 personnes ayant au moins deux images différentes**, ce qui le rend particulièrement adapté à l’entraînement de modèles de reconnaissance à l’aide de réseaux de neurones convolutifs (CNN).

Notre objectif est de :

- Prétraiter et organiser les images du dataset,
- Entraîner un modèle de classification (ou de vérification) de visages,
- Évaluer ses performances sur un ensemble de test non vu,
- Étudier les limites et axes d’amélioration du système.

---

## Résumé des essais réalisés

### Premier test : CNN simple

- Modèle basique avec 2 couches convolutionnelles et 1 couche dense finale.  
- Images redimensionnées à 64x64 pixels.  
- Résultat : **~15 % de précision** sur le test.  
- Limites : modèle trop simple, peu d’images par classe, pas d’augmentation des données, taille d’image faible.

---

### Deuxième test : CNN amélioré + augmentation de données

- Ajout d’une couche convolutionnelle supplémentaire et dropout pour éviter le sur-apprentissage.  
- Augmentation de données (rotation, zoom, translation, flip).  
- Filtrage plus strict : personnes avec au moins 3 images conservées.  
- Résultat : **~21 % de précision**.  
- Amélioration notable, mais encore insuffisant pour une reconnaissance fiable.

---

### Troisième test : Transfert learning avec MobileNetV2 pré-entraîné

- Images redimensionnées à 160x160 pixels (taille attendue par MobileNetV2).  
- Filtrage strict : minimum 15 images par personne pour un meilleur apprentissage.  
- Couches de MobileNetV2 gelées, ajout d’un classifieur personnalisé avec dropout.  
- Résultat : **~54 % de précision**.  
- Conclusion : le transfert learning apporte un vrai gain de performance grâce à l’utilisation de représentations visuelles pré-apprises.

---

## Points clés à retenir

- **Qualité des données** : avoir suffisamment d’exemples par personne est crucial.  
- **Augmentation des données** : nécessaire pour améliorer la robustesse du modèle.  
- **Taille d’image** : plus grande, plus d’informations et meilleures performances.  
- **Transfert learning** : méthode efficace pour exploiter des modèles pré-entraînés sur de larges bases et les adapter à des tâches spécifiques.

---

*Merci de consulter le code pour plus de détails sur les implémentations et les paramètres.*

