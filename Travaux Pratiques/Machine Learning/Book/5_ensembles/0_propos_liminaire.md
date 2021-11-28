Les méthodes *ensemblistes*
=======================

Lors des séquences précédentes, chaque modèle se suffisait à lui-même. Cependant, il est possible de les combiner afin d'améliorer les performances. Ce chapitre possède les séquences suivantes&nbsp;:

1. **Méthodes ensemblistes** - Cette séquence introduira un ensemble de méthodes à la fois formellement et au travers d'exemples paradigmatiques. Nous construirons tout d'abord une combinaison naïve de modèles (on vote !), puis nous formaliserons cela au travers du *framework* Bayésien ; ici, chaque modèle est associé à une certaine probabilité. On parle de *Bayesian Model Averaging*. Nous introduirons ensuite l'idée du *Boosting* qui cherche à exploiter les erreurs des précédents modèles afin de s'améliorer. Enfin, nous parlerons des forêts aléatoires qui combinent de nombreux arbres de classification ou de régression.
2. **Bayesian Linear Regression** - Le cas du *Bayesian Model Averaging* est particulier car il nous permet de considérer une infinité de modèles. Un de ces *setups* est la régression linéaire Bayésienne. On montrera comment dériver les équations de ce modèle ainsi que l'approche Ridge peut être vue comme en découlant.
