Guide Markdown : https://blog.wax-o.com/2014/04/tutoriel-un-guide-pour-bien-commencer-avec-markdown/

# Modèle des k plus proches voisins

## Classification k-NN

<pre><code>from sklearn.neighbors import KNeighborsClassifier
clf = KNeighborsClassifier(n_neighbors=n_neighbors).fit(X, y)</code></pre>

## Régression k-NN

<pre><code>from sklearn.neighbors import KNeighborsRegressor
reg = KNeighborsRegressor(n_neighbors=3)</code></pre>

****************************************************************************************************

# Modèles linéaires pour la régression

## Régression linéaire (ou méthode des moindres carrés ordinaires)

La régression linéaire, ou MCO pour moindres carrés ordinaires est la plus simple et la plus classique méthode linéaire pour la régression. La régression linéaire trouve les paramètres w et b qui minimisent la valeur de l'erreur quadratique moyenne (MSE) entre prédictions et cibles de la régression vraies, soit y, portant sur le jeu d'apprentissage. 

Formule de la régression linéaire :
<pre><code> ŷ = w[0]*x[0] + w[1]*x[1] + ... + w[p]*x[p] + b </code></pre>

L'erreur quadratique moyenne est la somme des différences au carré entre les prédictions et les valeurs réelles divisée par le nombre d'échantillons.

![MSE](https://cdn-media-1.freecodecamp.org/images/hmZydSW9YegiMVPWq2JBpOpai3CejzQpGkNG "MSE")

<pre><code>from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)</code></pre>

## Régression Ridge

Il s'agit également d'un modèle linéaire pour la régression, et donc la formule qu'il utilise pour faire des prédictions est la même que dans le cas des moindres carrés ordinaires. Dans la régression ridge, cependant, les coefficients (w) sont choisis non seulement de manière à ce qu'ils fournissent de bonnes prédictions sur le jeu d'apprentissage, mais aussi qu'ils remplissent une contrainte supplémentaire.

Nous voulons également que les coefficients de pondération soient aussi petits que possible. En d'autre termes, toutes les entrées de w devraient être proches de zéro. D'un point de vue intuitif, cela signifie que chaque caractéristique devrait avoir aussi peu d'impact que possible sur la sortie tout en fournissant de bonnes prédictions. Cette contrainte est un exemple de ce qui est appelé régularisation.

Cette régularisation signifie que l'on restreint explicitement un modèle pour éviter le surapprentissage. Le type particulier utilisé par la régression ridge est connu sous le nom de régularisation L2 (d'un point de vue mathématique, la méthode ridge pénalise le carré de la norme L2, ou encore la longueur euclidienne de w).

<pre><code>from sklearn.linear_model import Ridge
ridge = Ridge().fit(X_train, y_train)</code></pre>

Le modèle Ridge établit un compromis entre la simplicité du modèle (coefficients proches ce zéro) et les performances sur le jeu d'appentissage. L'importance relative entre ces deux pôles, simplicité d'une part et performance de l'autre peut être spécifiée par l'utilisateur à l'aide du paramètre alpha. Par défault, alpha = 1.0. 

Il n'y a cependant aucune raison pour que cela nous donne le meilleur compromis. La valeur optimale pour alpha dépend du jeu de données particulier que nous utilisons. 

Augmenter alpha force les coefficients à se rapprocher davantage de zéro, ce qui fait décroite les performances sur le jeu d'apprentissage mais peut aider à obtenir une meilleure généralisation

Abaisser la valeur d'alpha permet aux coefficients d'être moins restreints. Pour de très petites valeurs de ce paramètre, le modèle ressemble de plus en plus à une régression linéaire (les deux finissent par se confondre si alpha devient nul).

<pre><code>ridge10 = Ridge(aplha=10).fit(X_train, y_train)</code></pre>

## Lasso

Une alternative à ridge pour les régressions linéaires régularisées s'appelle Lasso (acronyme de Least Absolute Shrinkage and Selection Operator). Comme dans le cas de la régression ridge, la méthode lasso a pour but de contraindre les coefficients à se rapprocher de zéro, mais d'une manière un peu différente appelée régularisation L1 (en d'autres termes, elle pénalise la norme L1 du vecteur de pondération, c'est à dire la somme des valeurs absolues des coefficients au lieu de la moitié du carré de la norme L2).

La conséquence de la régularisation L1 est que, lorsque vous utilisez la régression lasso, certains coefficients valent exactement zéro. Cela signifie que certaines caractéristiques sont totalement ignorées par le modèle. Cela peut être vu comme une forme de sélection automatique des caractéristiques. Le fait que certains coefficients soient nuls rend souvent un modèle plus facile à interpréter, et peut également réveler quelles sont les caractéristiques les plus importantes du modèle.

<pre><code>from sklearn.linear_model import Lasso
lasso = Lasso().fit(X_train, y_train)</code></pre>

Comme ridge, la régression lasso a également un paramètre de régularisation, alpha, qui contrôle l'impact de la méthode sur la valeur des coefficients. Un paramètre qui peut être modifié est celui du nombre maximum d'itérations, max_iter. Par défaut, max_iter = 1000.

## Comparaisons des méthodes

En pratique, la régression ridge est généralement le premier choix à faire par rapport à lasso. Cependant, si vous avez une grande quantité de caractéristiques et que vous pensiez que quelques-unes seulement sont importantes, le modèle lasso pourrait être un meilleur choix.

De même, si vous voulez un modèle qui soit facile à interpréter, lasso fournit effectivement une solution bien mieux compréhensible du fait qu'elle ne sélectionne qu'un sous-ensemble des caractéristiques.


# Annexes

[Regularisation L1 & L2] (https://inside-machinelearning.com/regularization-deep-learning/ "link to regularization L1 & L2")

[Surappentissage et Regularisation] (https://bioinfo.iric.ca/fr/le-surapprentissage-et-la-regularisation/ "link to overfitting & regularization")