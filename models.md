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

Formule de la régression linéaire :
<pre><code> ŷ = w[0]*x[0] + w[1]*x[1] + ... + w[p]*x[p] + b </code></pre>

Les coefficients w et b l'erreur quadratique moyenne (MSE).

![MSE](https://www.google.com/imgres?imgurl=https%3A%2F%2Fwww.justintodata.com%2Fwp-content%2Fuploads%2F2020%2F05%2Fimage-7.png&imgrefurl=https%3A%2F%2Fwww.justintodata.com%2Flinear-regression-machine-learning-python-tutorial%2F&tbnid=no4DHhsM3-dYeM&vet=12ahUKEwiDlqm_y5L7AhVJVaQEHQ5NA2QQMygWegUIARDyAQ..i&docid=d_QDo8evOLOKSM&w=363&h=238&q=linear%20regression%20function&ved=2ahUKEwiDlqm_y5L7AhVJVaQEHQ5NA2QQMygWegUIARDyAQ "MSE")


<pre><code>from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)</code></pre>

## Régression Ridge
Minimisati
<pre><code>from sklearn.linear_model import Ridge
ridge = Ridge().fit(X_train, y_train)</code></pre>