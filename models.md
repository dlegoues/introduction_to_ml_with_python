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
{\displaystyle y_{i}=\beta _{0}+\beta _{1}x_{i,1}+\ldots +\beta _{K}x_{i,K}+\varepsilon _{i}}
<pre><code>from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)</code></pre>

## Régression Ridge
<pre><code>from sklearn.linear_model import Ridge
ridge = Ridge().fit(X_train, y_train)</code></pre>