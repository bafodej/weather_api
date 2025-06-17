# 🌤️ API Météo - Projet d'api rest python

## 📖 Description

Ce projet démontre l'utilisation avancée de l'API OpenWeatherMap avec Python  pour analyser les données météorologiques de plusieurs villes.

## 🎯 Fonctionnalités Implémentées

### ✅ Questions Traitées

1. **Interrogation dynamique multi-villes** - Automatisation Postman Runner
2. **Variables d'environnement** - Stockage conditions météo + scripts conditionnels
3. **Analyse feels_like** - Comparaison température réelle vs ressenti + IA contextuelle
4. **Dataset JSON structuré** - 5 villes + transformation pour ML
5. **Alertes température critique** - Seuils >40°C/<-20°C + génération automatique
6. **Lever/coucher soleil** - Détection jour/nuit via API
7. **Comparaisons automatisées** - Multi-villes sur 3+ indicateurs

## 🚀 Installation et Usage

### Prérequis
- Python 3.8+
- Jupyter Notebook
- Clé API OpenWeatherMap

### Installation
```bash
# Cloner le repository
git clone https://github.com/bafodej/weather-api-project.git
cd weather-api-project

# Installer les dépendances
pip install -r requirements.txt

# Configurer les variables d'environnement
cp .env.example .env
# Ajouter votre clé API dans .env
```

### Configuration
1. Créer un compte sur [OpenWeatherMap](https://openweathermap.org/api)
2. Obtenir votre clé API gratuite
3. Modifier le fichier `.env` :
```
CLIENT_ID=votre_api_key_openweather
```

### Lancement
```bash
# Démarrer Jupyter
jupyter notebook

# Ouvrir le fichier notebook.ipynb
```

## 📊 Exemples de Résultats

### Analyse Feels Like
```
🌡️ Paris:
   Température réelle: 22°C
   Ressenti: 24°C
   Différence: +2.0°C
   
🤖 INTERPRÉTATION IA:
   📊 Légère différence - conditions acceptables
```

### Comparaison Villes
```
🌍 COMPARAISON: Alger vs Montréal
🌡️ TEMPÉRATURE:
   Alger: 28°C
   Montréal: 15°C
   → Plus chaud: Alger
   
🏆 VERDICT: Alger = Plus chaud et sec
```

### Dataset JSON Généré
```json
{
  "cities": [
    {
      "name": "Paris",
      "temperature": 22.5,
      "humidity": 65,
      "weather_main": "Clear"
    }
  ]
}
```

## 🛠️ Technologies Utilisées

- **Python 3.8+** - Language principal
- **Requests** - Appels API REST
- **Jupyter Notebook** - Environnement de développement
- **OpenWeatherMap API** - Source des données météo
- **JSON** - Format de données structurées

## 📁 Structure du Projet

```
weather-api-project/
├── notebook.ipynb        # Notebook principal avec toutes les analyses
├── README.md             # Ce fichier
├── requirements.txt      # Dépendances Python
├── data/                 # Fichiers JSON générés
    ├── weather_dataset_*.json
    ├── comparaisons_*.json  └── alerte_*.json
              

```

## 🔧 Fonctions Principales

### `get_weather(city)`
Récupère les données météo d'une ville via l'API OpenWeatherMap.

### `analyze_feels_like(city)`
Analyse la différence entre température réelle et ressenti avec interprétation IA.

### `create_weather_dataset()`
Génère un dataset JSON structuré de 5 villes pour l'analyse ML.

### `compare_cities_advanced(city1, city2)`
Compare deux villes sur multiple indicateurs météorologiques.

### `check_critical_temperature_alert()`
Système d'alerte automatique pour températures critiques.

## 📈 Transformation pour Machine Learning

Le projet inclut des fonctions pour transformer les données JSON en format exploitable pour l'apprentissage automatique :

- **Features numériques** : température, humidité, pression
- **Features catégorielles** : conditions météo, pays
- **Feature engineering** : différence feels_like, indices de confort
- **Preprocessing** : normalisation, encoding, gestion des valeurs manquantes


### Runner Automatique
Scripts fournis pour automatiser l'interrogation de multiples villes via Postman Runner.

### Variables d'Environnement
Configuration dynamique pour tester différentes villes sans modifier les requêtes.

## 📊 Exemples d'Alertes

### Alerte Canicule (>40°C)
```json
{
  "type": "CANICULE",
  "city": "Las Vegas",
  "temperature": 42,
  "severity": "CRITIQUE",
  "actions": [
    "Hydratation constante",
    "Éviter sorties 11h-16h"
  ]
}
```

## 🙏 Remerciements

- [OpenWeatherMap](https://openweathermap.org/) pour l'API gratuite
- Communauté Python pour les bibliothèques excellentes
- Documentation Postman pour l'automatisation
