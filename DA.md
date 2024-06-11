# NumPy, Pandas, Matplotlib, Seaborn, sklearn
## Numpy

Numpy ist eine Python library für numerische Berechnung und Operationen auf Arrays. Numpy wird in der Datenanalyse verwendet.

### Numpy Array

```Python
arr = np.array([10,20,30,40,50])

#oder mehr dimensional

arr_2d = np.array([
    [10, 20, 30, 40, 50],
    [100, 200, 300, 400, 500]
])
```
### Form des arrays

```Python
print(arr_2d.shape)
# output: (2, 5)
# 2 Dimensionen, 5 werte/Dimension
```
Bei einem Numpy Array sollten alle Stellen den gleichen Datentypen haben.

## Pandas

Pandas wird für die Datenmanipulation und -analyse von Daten in Tabellen Struktur verwendet. Die wichtigste Funktion ist der Dataframe, welche z.B. ein CSV-File als Variable im Code abbilden kann.

### CSV einlesen

```Python
df = pd.read_csv("../data/temp.csv")
```
### Die ersten 5 Zeile
```Python
df.head()
```
### Alle NaN werte entfernen (Datenaufbereitung)
```Python
df.dropna()
```
### Tabelle sortieren
```Python
df.sort_values(by=[spaltenname])
```
## Matplotlib
Matplotlib wird für die Visualisierung von daten verwendet, z.B. Diagramme, Plots, Grafiken

### Beispiel für die Visualisierung
```Python
import matplotlib.pyplot as plt

# Daten für die Zeit und Temperatur
zeitpunkte = [0, 1, 2, 3, 4, 5]
temperaturen = [20, 22, 25, 27, 23, 21]

# Erstellen des Plots
plt.plot(zeitpunkte, temperaturen, marker='o', linestyle='-')

# Beschriftungen für Achsen und Titel
plt.xlabel('Zeit (Stunden)')
plt.ylabel('Temperatur (°C)')
plt.title('Temperaturverlauf')

plt.show()
```
## Seaborn
Die Seaborn library setzt auf Matlpotlib auf um komplexere Visualisierungen zu ermöglichen.

### Beispiel Visualisierung mit Seaborn und Matplotlib
```Python
import seaborn as sns
import matplotlib.pyplot as plt

# Daten für die Zeit und Temperatur
zeitpunkte = [0, 1, 2, 3, 4, 5]
temperaturen = [20, 22, 25, 27, 23, 21]

# Setzen des Stils für Seaborn
sns.set_style("whitegrid")

# Erstellen des Plots mit Seaborn
sns.lineplot(x=zeitpunkte, y=temperaturen, marker='o')

# Beschriftungen für Achsen und Titel
plt.xlabel('Zeit (Stunden)')
plt.ylabel('Temperatur (°C)')
plt.title('Temperaturverlauf')

plt.show()
```

## Sklearn
Sklearn ist eine Open-Source-Library für die Verwendung von Machine Learning Algorithmen wie z.B. Regression, Supervised Learning oder Unsupervised Learning.

### Beispiel Lineare Regression
```Python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import numpy as np

# Erzeugen von Beispieldaten
X = np.array([[1], [2], [3], [4], [5]])  # Features (unabhängige Variable)
y = np.array([2, 4, 5, 4, 5])  # Zielvariable (abhängige Variable)

# Aufteilen der Daten in Trainings- und Testsets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialisierung und Training des linearen Regressionsmodells
model = LinearRegression()
model.fit(X_train, y_train)

# Vorhersage auf den Testdaten
y_pred = model.predict(X_test)

# Auswertung des Modells
mse = mean_squared_error(y_test, y_pred)
print("Mean Squared Error:", mse)

# Visualisierung der Daten und der Regressionsgeraden
import matplotlib.pyplot as plt

plt.scatter(X, y, color='blue')
plt.plot(X_test, y_pred, color='red', linewidth=2)
plt.xlabel('Feature')
plt.ylabel('Zielvariable')
plt.title('Lineare Regression')
plt.show()
```
