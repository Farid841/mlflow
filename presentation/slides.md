---
theme: seriph
background: https://cover.sli.dev
title: MLflow Presentation
info: |
  ## MLflow Presentation
  A Tool for Managing the Machine Learning Lifecycle
  Learn more at [MLflow Documentation](https://mlflow.org)
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

# MLFLOW

A Tool for Managing the Machine Learning Lifecycle

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/Farid841/mlflow" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

---
transition: fade-out
---

# Qu'est-ce que MLflow ?

MLflow est une plateforme open source pour gérer le cycle de vie du machine learning.

**Objectif :** faciliter le suivi, la reproductibilité et la collaboration sur les projets ML


---
transition: fade-out
---

<div class="text-center mt-8">



## Principales fonctionnalités

</div>

<div class="grid grid-cols-2 gap-6 mt-8">

<div class="bg-blue-50 dark:bg-blue-900/20 p-6 rounded-lg border border-blue-200 dark:border-blue-700">
  <div class="text-2xl mb-3">🔬</div>
  <h3 class="font-bold text-lg mb-2">MLflow Tracking</h3>
  <p class="text-sm">Suivi des expériences, métriques et paramètres</p>
</div>

<div class="bg-green-50 dark:bg-green-900/20 p-6 rounded-lg border border-green-200 dark:border-green-700">
  <div class="text-2xl mb-3">📦</div>
  <h3 class="font-bold text-lg mb-2">MLflow Projects</h3>
  <p class="text-sm">Format pour empaqueter le code ML de manière reproductible</p>
</div>

<div class="bg-purple-50 dark:bg-purple-900/20 p-6 rounded-lg border border-purple-200 dark:border-purple-700">
  <div class="text-2xl mb-3">🚀</div>
  <h3 class="font-bold text-lg mb-2">MLflow Models</h3>
  <p class="text-sm">Format standard pour déployer des modèles ML</p>
</div>

<div class="bg-orange-50 dark:bg-orange-900/20 p-6 rounded-lg border border-orange-200 dark:border-orange-700">
  <div class="text-2xl mb-3">📊</div>
  <h3 class="font-bold text-lg mb-2">MLflow Model Registry</h3>
  <p class="text-sm">Gestion centralisée des modèles et de leurs versions</p>
</div>

</div>

<div class="text-center mt-8">

En savoir plus : [Documentation MLflow](https://mlflow.org/docs/latest/index.html)

</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: two-cols
---

# Problèmes sans MLflow

<v-click>

## ❌ Défis courants

- 📝 Perte d'informations sur les expériences
- 🔄 Difficulté à reproduire les résultats
- 📦 Gestion manuelle et dispersée des modèles
- 👥 Collaboration complexe entre équipes
- ⏱️ Temps perdu à retrouver les configurations

</v-click>

::right::

<v-click>

## ✅ Solutions MLflow

- 🎯 Suivi automatique des expériences
- 🔒 Reproductibilité garantie
- 📊 Centralisation des modèles
- 🤝 Collaboration simplifiée
- ⚡ Gain de temps et d'efficacité

</v-click>

---
layout: default
---

# MLflow Tracking

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

## 📊 Enregistrement des expériences

```python {all|1-2|4-5|7-10|12-14|16-17|all}
import mlflow
from sklearn.ensemble import RandomForestClassifier

# Démarrer un run MLflow
mlflow.start_run()

# Enregistrer les paramètres
mlflow.log_param("n_estimators", 100)
mlflow.log_param("max_depth", 10)
mlflow.log_param("random_state", 42)

# Entraîner le modèle
model = RandomForestClassifier(n_estimators=100, max_depth=10)
model.fit(X_train, y_train)

# Enregistrer les métriques
accuracy = model.score(X_test, y_test)
mlflow.log_metric("accuracy", accuracy)

# Sauvegarder le modèle
mlflow.sklearn.log_model(model, "model")

mlflow.end_run()
```

</div>

<div>

<v-click>

## 🖥️ Interface Web

L'interface MLflow permet de :

- 📈 Visualiser tous les runs
- 🔍 Comparer les métriques
- ⚙️ Explorer les paramètres
- 💾 Télécharger les artefacts

<div class="mt-6 p-4 bg-blue-50 dark:bg-blue-900/20 rounded-lg">
  <p class="text-sm font-bold">💡 Lancer l'interface :</p>
  <code class="text-xs">mlflow ui</code>
  <p class="text-xs mt-2">Accessible sur http://localhost:5000</p>
</div>

</v-click>

</div>

</div>

---
layout: default
---

# Model Registry

<div class="grid grid-cols-3 gap-6 mt-8">

<v-click>

<div class="p-6 border-2 border-blue-300 rounded-lg bg-blue-50/50 dark:bg-blue-900/10">

## 1️⃣ Enregistrement

```python
mlflow.register_model(
    model_uri="runs:/abc123/model",
    name="mon_modele"
)
```

Création d'un modèle versionné dans le registre

</div>

</v-click>

<v-click>

<div class="p-6 border-2 border-green-300 rounded-lg bg-green-50/50 dark:bg-green-900/10">

## 2️⃣ Promotion

```python
client.transition_model_version_stage(
    name="mon_modele",
    version=1,
    stage="Production"
)
```

Passage de Staging à Production

</div>

</v-click>

<v-click>

<div class="p-6 border-2 border-purple-300 rounded-lg bg-purple-50/50 dark:bg-purple-900/10">

## 3️⃣ Chargement

```python
model = mlflow.pyfunc.load_model(
    "models:/mon_modele/Production"
)
predictions = model.predict(data)
```

Utilisation du modèle en production

</div>

</v-click>

</div>

<v-click>

<div class="mt-8 p-6 bg-yellow-50 dark:bg-yellow-900/20 rounded-lg">

### 🎯 Avantages du Model Registry

- ✅ Versioning automatique des modèles
- ✅ Traçabilité complète (qui, quand, pourquoi)
- ✅ Gestion des transitions de stage
- ✅ Rollback facile en cas de problème

</div>

</v-click>

---
layout: default
---

# Workflow typique avec MLflow

<v-clicks depth="2">

## 1. 🏃 Entraînement avec Tracking

```python
with mlflow.start_run():
    mlflow.log_params({"learning_rate": 0.01, "epochs": 50})
    # ... entraînement du modèle ...
    mlflow.log_metrics({"loss": final_loss, "accuracy": acc})
    mlflow.sklearn.log_model(model, "model")
```

## 2. 👀 Visualisation et comparaison

- Ouvrir l'interface web MLflow (`mlflow ui`)
- Comparer les différents runs
- Identifier le meilleur modèle

## 3. 📦 Enregistrement dans le Registry

```python
mlflow.register_model("runs:/run_id/model", "mon_modele_v2")
```

## 4. 🚀 Déploiement en production

```python
# Promotion en production
client.transition_model_version_stage(
    name="mon_modele_v2", version=2, stage="Production"
)

# Déploiement comme service REST
mlflow models serve -m "models:/mon_modele_v2/Production" -p 5001
```

</v-clicks>

---
layout: two-cols
layoutClass: gap-8
---

# Bénéfices pour l'équipe

<v-click>

## 👥 Collaboration

- Centralisation de toutes les informations
- Partage facile des expériences
- Travail d'équipe simplifié
- Historique complet des modifications

</v-click>

<v-click>

## 🔄 Reproductibilité

- Suivi automatique des expériences
- Environnements reproductibles
- Paramètres et versions sauvegardés
- Restauration facile des anciens modèles

</v-click>

::right::

<v-click>

## ⚡ Efficacité

- Gain de temps significatif
- Réduction des erreurs humaines
- Automatisation des tâches répétitives
- Focus sur l'expérimentation

</v-click>

<v-click>

## 🎯 Polyvalence

- ML traditionnel (scikit-learn, XGBoost)
- Deep Learning (PyTorch, TensorFlow)
- Tout framework Python
- Workflows personnalisables

</v-click>

---
layout: center
class: text-center
---

# Conclusion

<v-clicks>

<div class="text-2xl font-bold mt-8">
✨ MLflow simplifie et fiabilise la gestion des projets ML
</div>

<div class="mt-8 text-left max-w-2xl mx-auto">

### Pourquoi adopter MLflow ?

- 🎯 Outil **incontournable** pour les équipes data science et MLOps
- 🚀 Accélère le développement et le déploiement des modèles
- 🔒 Garantit la traçabilité et la gouvernance
- 💰 Open source et gratuit
- 🌍 Large communauté et écosystème riche

</div>

<div class="mt-12 text-3xl">

## 💬 Questions ?

</div>

</v-clicks>

---
layout: end
class: text-center
---

# Merci !

Des questions sur MLflow ?

<div class="mt-8 text-sm opacity-75">
  Présentation créée avec Slidev
</div>

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/Farid841/mlflow" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>