# Analyse de la qualité du vin - Approche par neurones et MLP

Ce projet fait partie d'un TP visant à analyser les données d'un dataset choisi par nos soins. Dans ce cas, nous avons utilisé un dataset sur la **qualité des vins**. L'objectif est d'appliquer les techniques apprises en cours pour déterminer si un vin est de "bonne qualité" ou de "mauvaise qualité" en fonction de ses caractéristiques chimiques.

## Ce qui a été produit
1. Comprendre et mettre en œuvre un modèle de **neurone simple** pour classifier les vins.
2. Identifier les limites d'un neurone simple dans ce contexte.
3. Élaborer et entraîner un **MLP (Multi-Layer Perceptron)** pour une classification plus précise.
4. Comparer les performances des deux méthodes (neurone simple et MLP).

## Structure du projet

### 1. **Dataset**
Les étiquettes de qualité sont binarisées :
- **1** : Bonne qualité (score >= 6).
- **0** : Mauvaise qualité (score < 6).

### 2. **Approches implémentées**

#### **2.1 Neurone simple**
Un perceptron (neurone simple) a été implémenté pour effectuer une classification binaire. Il prend en entrée les caractéristiques chimiques des vins et applique une fonction de somme pondérée suivie d'une règle de décision simple.

- **Limites constatées** :
  - Un neurone simple ne peut tracer qu'une frontière linéaire pour séparer les classes.
  - Les données étant non linéairement séparables, la précision obtenue était limitée.

#### **2.2 Multi-Layer Perceptron (MLP)**
Pour surmonter les limites du perceptron, un MLP a été implémenté. Le MLP comporte plusieurs couches cachées avec des fonctions d'activation non linéaires, permettant d'apprendre des relations plus complexes entre les données.

- **Configuration** :
  - Deux couches cachées initiales : (8, 5) neurones.
  - Ajout progressif de couches et d'optimisations (32, 16, 8) pour améliorer les performances.

- **Avantages** :
  - Une capacité accrue à capturer les motifs complexes dans les données.
  - Une précision significativement améliorée par rapport au neurone simple.

### 3. **Comparaison des résultats**
Les deux modèles ont été comparés sur leur capacité à classifier correctement les vins en "bonne" ou "mauvaise" qualité.

| Modèle           | Précision |
|-------------------|-----------|
| Neurone simple   | ~70%      |
| MLP optimisé     | ~79%      |

Malgré l'amélioration avec le MLP, la précision pourrait être augmentée davantage avec des données supplémentaires ou un ajustement des hyperparamètres.

### 4. **Exemples de test**
Des exemples de vins spécifiques (comme **Chablis**, **La Turque**, et **Monbazillac**) ont été testés pour vérifier si le modèle pouvait identifier correctement leur qualité. Les caractéristiques chimiques utilisées pour ces exemples sont :

- **Chablis** : `[7.0, 0.3, 0.4, 1.2, 0.045, 15.0, 75.0, 0.992, 3.35, 0.7, 12.5]`
- **La Turque** : `[6.5, 0.4, 0.35, 1.8, 0.05, 18.0, 85.0, 0.994, 3.65, 0.75, 13.5]`
- **Monbazillac** : `[5.5, 0.3, 0.4, 120.0, 0.05, 35.0, 150.0, 1.020, 3.6, 0.6, 13.0]`

Ces exemples ont été soumis au modèle MLP pour prédire leur qualité. De plus, les mêmes exemples ont été testés avec un modèle de **decision tree** pour vérifier la cohérence des résultats. Les prédictions obtenues avec les deux modèles étaient concordantes, confirmant ainsi la véracité des données utilisées.

Cette validation croisée a renforcé la confiance dans les résultats et a démontré que les modèles étaient capables d'identifier correctement des vins spécifiques en fonction de leurs caractéristiques chimiques.

## Conclusion

Ce projet met en lumière les forces et les faiblesses des modèles de neurones simples et des MLP dans la classification, tout en montrant l'importance de la validation croisée avec d'autres modèles.

- Le **neurone simple** offre une solution rapide et intuitive, mais reste limité par sa capacité à tracer uniquement des frontières de décision linéaires. Cela le rend moins efficace pour des données complexes et non linéaires, comme celles utilisées dans ce projet.

- En revanche, le **MLP (Multi-Layer Perceptron)** permet d'exploiter des relations non linéaires entre les caractéristiques, grâce à ses couches cachées et ses fonctions d'activation. Cela en fait un outil beaucoup plus puissant et adapté pour ce type de tâche.

De plus, les prédictions obtenues ont été vérifiées à l'aide d'un **decision tree** sur des exemples spécifiques (Chablis, La Turque, Monbazillac). Cette validation croisée a confirmé la cohérence des résultats et la fiabilité des données utilisées.

