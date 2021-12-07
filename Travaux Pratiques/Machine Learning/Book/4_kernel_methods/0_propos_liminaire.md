Les méthodes à noyaux
=======================

Les méthodes à noyaux définissent une famille permettant de calculer des fonctions linéaires ET non-linéaires. Le principe de ces méthodes est de s'appuyer sur la similarité entre les points calculées au travers d'un produit scalaire. Toute l'astuce viendra de l'espace dans lequel ce produit scalaire est calculé, permettant par là même de d'obtenir des solutions non linéaires. Il se trouve qu'il est possible de remplacer la transformation dans un espace suivie du produit scalaire de "similarité" par ce qu'on appelle un noyau. Cette astuce nous permet même de considérer des espaces de dimension infinie ! Ce chapitre se construit autour des séquences suivantes&nbsp;:


1. **Le SVM** - Cette séquence introduira le SVM au travers de sa formulation théorique. Nous montrerons ensuite que ce problème peut être vu au travers de son "dual" permettant ce qu'on appelle l'astuce du noyau. Cette dernière offre des avantages computationnelles lorsqu'on cherche à résoudre des problèmes non linéaires.
