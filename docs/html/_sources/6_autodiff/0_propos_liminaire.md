La différentiation automatique
=======================

Lors des séquences précédentes, nous avons pu voir que l'optimisation était une étape clé de l'optimisation. Cette optimisation nécessitait souvent le calcul du gradient de notre fonction de coût. Ce gradient, même dans les cas simples est compliqué à calculer. La force des *framework* de *deep learning* est de s'appuyer sur la différentiation automatique. Le gradient n'est pas à fournir par l'utilisateur, mais calculé directement par le *framework*. C'est ce que nous allons voir ici.
