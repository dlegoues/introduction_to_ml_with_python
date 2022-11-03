# Modèle des k plus proches voisins 

## Classification k-NN
<pre><code>from sklearn.neighbors import KNeighborsClassifier
clf = KNeighborsClassifier(n_neighbors=n_neighbors).fit(X, y)</code></pre>

## Régression k-NN
<pre><code>from sklearn.neighbors import KNeighborsRegressor
reg = KNeighborsRegressor(n_neighbors=3)</code></pre>


# Modèles linéaires

## Régression linéaire (ou méthode des moindres carrés ordinaires)
<pre><code>from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)</code></pre>