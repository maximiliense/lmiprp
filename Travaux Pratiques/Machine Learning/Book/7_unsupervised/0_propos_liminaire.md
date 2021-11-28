L'apprentissage non-supervisé
=======================

Nous considérons ici un paradigme d'apprentissage différent de l'approche supervisée où l'obectif cette fois ci n'est pas de prédire une variable d'intérêt $y$ en fonction d'autres variables $\boldsymbol{x} = \{x_1, x_2, \dots, x_d \} \in \mathcal{X} \subset \mathbb{R}^d$ mais plutôt de capturer certaines régularités statistiques entre les variables d'observation $x_j$ (*e.g.* des cooccurrences fréquentes de certains motifs dans des images) à partir d'un ensemble d'apprentissage $\mathcal{S}_n = \{\boldsymbol{x}_i\}_{i\leq n} \sim \mathbb{P}^n$. L'idée générale est de se dire qu'une réalisation jointe des variables observées $x_j$ (une instanciation particulière d'un objet sous la forme des pixels d'une image par exemple) correspond à un ensemble d'information complètement mélangées, non structurées (un où plusieurs concept peuvent être représentés visuellement sur plusieurs pixels). Il est ainsi difficile d'identifier les parties importantes du signal d'origine qui vont nous servir à résoudre une tâche de *machine learning* tout en évitant le problème de la malédiction de la dimensionalité et sur-apprentissage. L'idée de l'apprentissage de représentation est de trouver une procédure déterministe ou stochastique permettant de passer de ce statut d'information mélangées $x$ à une version plus structurée et moins redondante $\boldsymbol{z} = \{z_1, z_2, \dots, z_k \} \in \mathcal{Z} \subset \mathbb{R}^k$ qui correspondra à une représentation abstraite de $x$. L'idée est ensuite d'utiliser $z$ plutôt que $x$ pour résoudre une tâche de *machine learning* potentiellement à moindre coût en complexité d'échantillonage et à partir d'une classe de fonctions moins complexe.

Pour les approches déterministes, il s'agit souvent d'apprendre un changement de variables&nbsp:

$$\begin{aligned}
\Phi : \mathcal{X} &\rightarrow \mathcal{Z} \subset \mathbb{R}^K\\
\boldsymbol{x} &\mapsto \boldsymbol{z} = \Phi(\boldsymbol{x}) \end{aligned}$$

 qui associe à tout exemple d'apprentissage une image $\boldsymbol{z}$ telles que certaines "régularités utiles" dans l'espace d'origine soient conservées ou bien telles que les représentations soient contraintes à posséder certaines propriétés. On réalisera souvent cette opération par optimisation sous contraintes ou régularisées où la fonction objectif consiste par exemple à minimiser la distorsion entre le signal d'origine et une reconstruction de ce dernier à partir de sa représentation $z$ via un mapping "inverse"&nbsp;:

$$\begin{aligned}
\Psi : \mathcal{Z} &\rightarrow \mathbb{R}^d\\
\boldsymbol{z} &\mapsto \hat{\boldsymbol{x}} = \Psi(\boldsymbol{z}).\end{aligned}$$

Il existe un vision complémentaire probabiliste, parfois une généralisation, aux approches déterministes, où l'objectif va être de trouver non pas un *mapping* déterministe mais une distribution jointe $q_{\theta}(x ,z)$ dans une classe de distributions possibles $\mathcal{Q}$ et on cherche à trouver des représentations $z$ telles qu'on veut maximiser la probabilité d'être échantillonnées conjointement avec des variables observées $x$. On appelle ces méthodes les modèles génératifs à variables latentes car l'idée générale est d'apprendre à reproduire le processus générateur des données $\mathbb{P}$ où du moins une approximation de ce dernier de sorte à identifier les variables latentes ou les facteurs explicatifs associés aux données comme représentation de ces dernières. Dans ce cas là, l’inférence est souvent difficile et nécessite des approches de type Monte Carlo (i.e. simulations stochastiques $z \sim q_{\theta}(z|x)$), mais pas nécessairement (e.g. algorithme EM).

L'apprentissage de représentation est aujourd'hui un problème très vaste et il n'existe pas un consensus quant aux critères pour obtenir de "bonnes représentations" des données. En pratique, on fixe le processus générateurs comme hypothèse afin de contraindre nos données à posséder certaines propriétés. On peut le faire en pratique sous la forme d'optimisation sous contraintes ou de régularisation sur les représentations ou encore en jouant sur le biais inductif de la classe de fonctions/modèle génératifs dans laquelle on cherche notre *mapping* candidat. Les propriétés souhaitées et la nature de ce que devrait contenir ses réprésentation dépends largement de la tâche de *machine learning* cible qui suivra. Les applications sont multiples&nbsp;:

1.   Réduire les effets la malédiction de la dimensionalité qui est un gros facteur de sur-apprentissage pour les algorithmes supervisés. Apprendre des représentations plus parcimonieuses qui conservent l'essentiel de l'information de départ (dont celles nécéssaires pour prédire la variable cible) peut donc s'avérer un puissant mécanisme de régularisation.
2.   Recherche par similarité sémantique&nbsp;: trouver dans une grande collection d'images pour lesquelles nous ne disposons pas de tags celles qui sont le plus similaires à une requête.
3.   Découverte de tendances par partitionnement (*clustering*)&nbsp;: découvrir l'existence de groupes dont les membres présentent des similarités.

Ce chapitre se structure de la manière suivante&nbsp;:

1.  **L’Analyse en Composante Principales** - Il s’agit d’un exemple paradigmatique au travers d’une approche non-supervisée linéaire,
2. **L’apprentissage de dictionnaire** - Nous verrons ensuite que l’ACP peut se généraliser à des approches linéaires de la famille des apprentissage de dictionnaires,
3. **K-Means et les modèles de mélange Gaussien** - Nous verrons enfin une alternative probabiliste à ces modèles correspondant aux modèles à variables latentes.
