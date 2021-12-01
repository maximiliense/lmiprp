Prédiction d'ensembles
=======================

Nous avons vu jusque là comment gérer des problèmes de classification binaire où $\mathcal{Y}=\{0, 1\}$, multi-classes avec $\mathcal{Y}=\{1, \ldots, C\}$ ou encore de régression $\mathcal{Y}\subseteq\mathbb{R}$. Cependant, il peut arriver que nous devions gérer des problèmes où chaque donnée n'est pas associée à une unique classe mais à un ensemble de classes possible : on veut prédire un ensemble. Cela peut venir d'une incertitude intrinsèque à nos données (on parle d'incertitude aléatorique) qui sont réellement associées à plusieurs labels. Cela peut également venir d'une incertitude du modèle (on parle d'incertitude épistémique). Cette dernière incertitude pourrait se résoudre en collectant plus de données. 

Ce chapitre se décompose de la manière suivante&nbsp;:
*  **Jeu d’apprentissage set-valued** - Cette séquence abordera le problème dans le cas où nous disposons de cette information d'ensemble. On parlera aussi de problème "multi-labels".
*  **Jeu d’apprentissage uniquement multi-classes** - Cette séquence abordera le problème dans le cas où nous ne disposons pas de l'information d'ensemble et où chaque donnée n'est associée qu'à un unique label.
