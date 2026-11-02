# Customer Lifetime Value Prediction & Churn Survival Analysis

Projet Data Mining de bout en bout : analyse du comportement d'achat des clients d'une entreprise e-commerce, prédiction de la **Customer Lifetime Value (CLV)** et analyse de survie du **churn**, à partir du dataset **Online Retail II (UCI)**.

## Objectifs

- Comprendre le comportement d'achat des clients (fréquence, récence, montant).
- Prédire la valeur future des clients (CLV).
- Estimer la probabilité et le moment du churn avec l'analyse de survie.
- Segmenter les clients et prioriser les actions marketing.

## Dataset

- **Source** : [Online Retail II – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- **Contenu** : transactions d'un détaillant en ligne britannique (factures, produits, quantités, prix, clients, pays, dates).

## Hypothèses et contraintes

| Élément | Choix |
|---|---|
| Marge | 30 % |
| Définition du churn | 180 jours sans achat (seuils testés : 90 / 180 / 270) |
| Clients actifs | Censurés à droite |
| Validation | Split temporel (pour éviter le data leakage) |
| Deep Learning | Non utilisé |

## Méthodologie

1. **Nettoyage des données** : suppression des valeurs manquantes, des retours/annulations et des doublons.
2. **Feature engineering** : variables RFM (Recency, Frequency, Monetary), panier moyen, ancienneté, etc.
3. **Modélisation CLV** :
   - Baseline
   - Régression linéaire
   - Random Forest
   - Gradient Boosting / XGBoost
4. **Analyse de survie (churn)** :
   - Kaplan-Meier
   - Modèle de Cox (Proportional Hazards), objectif C-index > 0.60
   - Modèle de Weibull
5. **Segmentation** en 4 segments : *Champions*, *Potential Loyalists*, *At Risk*, *Low Value*.
6. **Score de priorité marketing** combinant CLV prédite et risque de churn.
7. **Export des données** prêtes pour un dashboard **Power BI**.

## Résultats

> À compléter après exécution du notebook (métriques des modèles, C-index, taille des segments, visualisations).

## Structure du projet

```
Customer-Lifetime-Value-Prediction/
├── data/                # Dataset Online Retail II
├── notebooks/           # Notebook Google Colab
├── outputs/             # Figures et fichiers exportés (Power BI)
├── requirements.txt
└── README.md
```

## Technologies

- Python
- pandas, NumPy
- scikit-learn, XGBoost
- lifelines (Kaplan-Meier, Cox, Weibull)
- matplotlib, seaborn
- Google Colab, Power BI

## Installation et exécution

```bash
git clone https://github.com/<votre-utilisateur>/Customer-Lifetime-Value-Prediction.git
cd Customer-Lifetime-Value-Prediction
pip install pandas numpy scikit-learn xgboost lifelines matplotlib seaborn openpyxl
```

Puis ouvrir le notebook dans Jupyter ou Google Colab et exécuter les cellules dans l'ordre.

## Auteur

**Hiba** – Master IAII (Intelligence Artificielle et Ingénierie Informatique), FST Marrakech.
