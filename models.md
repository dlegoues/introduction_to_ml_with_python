# Modèle des k plus proches voisins 

## Classification k-NN
from sklearn.neighbors import KNeighborsClassifier
clf = KNeighborsClassifier(n_neighbors=n_neighbors).fit(X, y)

## Régression k-NN
from sklearn.neighbors import KNeighborsRegressor
reg = KNeighborsRegressor(n_neighbors=3)


# Modèles linéaires

## Régression linéaire (ou méthode des moindres carrés ordinaires)
from sklearn.linear_model import LinearRegression
lr = LinearRegression().fit(X_train, y_train)