Guide Markdown : https://blog.wax-o.com/2014/04/tutoriel-un-guide-pour-bien-commencer-avec-markdown/

# Modèle des k plus proches voisins

## Classification k-NN

Python :
<pre><code>from sklearn.neighbors import KNeighborsClassifier
clf = KNeighborsClassifier(n_neighbors=n_neighbors).fit(X, y)</code></pre>

## Régression k-NN

Python :
<pre><code>from sklearn.neighbors import KNeighborsRegressor
reg = KNeighborsRegressor(n_neighbors=3)</code></pre>

****************************************************************************************************

# Modèles linéaires

## Régression linéaire (ou méthode des moindres carrés ordinaires)

Formule de la régression linéaire :
<pre><code> ŷ = w[0]*x[0] + w[1]*x[1] + ... + w[p]*x[p] + b </code></pre>

La régression linéaire trouve les paramètres w et b qui minimisent la valeur de l'erreur quadratique moyenne (MSE) entre prédictions et cibles de la régression.
![MSE](https://cdn-media-1.freecodecamp.org/images/hmZydSW9YegiMVPWq2JBpOpai3CejzQpGkNG "MSE")

Python :
<pre><code>from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)</code></pre>

## Régression Ridge
Python :
<pre><code>from sklearn.linear_model import Ridge
ridge = Ridge().fit(X_train, y_train)</code></pre>