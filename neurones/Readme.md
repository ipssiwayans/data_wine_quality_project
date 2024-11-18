# Potentielle explication pour la différence de performance entre un neurone simple et un MLP

## Données d'entrée
Les exemples que vous utilisez ont des valeurs complexes et variées (densité, pH, alcool, etc.). Certaines caractéristiques pourraient jouer un rôle important pour le MLP mais être négligées par le neurone simple.

### Exemple de données d'entrée
- Chablis : [7.0, 0.3, 0.4, 1.2, 0.045, 15.0, 75.0, 0.992, 3.35, 0.7, 12.5]
- La Turque : [6.5, 0.4, 0.35, 1.8, 0.05, 18.0, 85.0, 0.994, 3.65, 0.75, 13.5]
- Monbazillac : [5.5, 0.3, 0.4, 120.0, 0.05, 35.0, 150.0, 1.020, 3.6, 0.6, 13.0]

On peut voir que les valeurs sont très différentes pour chaque caractéristique. Le neurone simple pourrait ne pas être capable de traiter ces données de manière efficace.

En effet dans le neurone simple le monbazillac est de bonne qualité alors qu'avec le MLP il est de mauvaise qualité.

Dans la réalité le monbazillac est considéré comme de mauvaise qualité.