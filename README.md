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
