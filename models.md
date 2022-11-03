Guide Markdown : https://blog.wax-o.com/2014/04/tutoriel-un-guide-pour-bien-commencer-avec-markdown/

# Modèle des k plus proches voisins

## Classification k-NN

<pre><code>from sklearn.neighbors import KNeighborsClassifier
clf = KNeighborsClassifier(n_neighbors=n_neighbors).fit(X, y)</code></pre>

## Régression k-NN

<pre><code>from sklearn.neighbors import KNeighborsRegressor
reg = KNeighborsRegressor(n_neighbors=3)</code></pre>

****************************************************************************************************

# Modèles linéaires

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