# AGENTS.md

## Portee du projet
- Projet de cours ML pour prediction de serie temporelle (README: `Global_active_power`, metriques MSE/MAE/RMSE).
- Le repo est notebook-first: `notebook.ipynb` est l'unique source de travail modelisation.
- Les dependances sont strictement epinglees dans `requirements.txt` (TensorFlow/Keras/Pandas/Matplotlib/Seaborn).

## Architecture reelle (etat actuel)
- `notebook.ipynb` contient surtout un squelette pedagogique (cellules `#%%` / `#%% md`) et des consignes, pas un pipeline complet deja code.
- Flux attendu (a implementer dans le notebook):
  1) chargement/exploration du dataset temporel,
  2) nettoyage + normalisation,
  3) windowing temporel,
  4) split chronologique train/val/test,
  5) entrainement/comparaison SimpleRNN vs LSTM vs GRU,
  6) evaluation + visualisation predictions.
- Frontiere de service: aucune API/backend; tout se passe localement dans Python/Jupyter.

## Workflow developpeur critique
- Creer l'environnement puis installer les versions exactes:
  - `pip install -r requirements.txt`
- Ouvrir et executer `notebook.ipynb` cellule par cellule (ordre temporel important).
- Dataset non versionne: recuperation manuelle via UCI (README), puis filtrage d'une periode limitee.
- Le repo ne fournit ni suite de tests automatisee ni script `train.py`; valider via sorties notebook (courbes + metriques).

## Conventions specifiques a respecter
- Garder l'experimentation dans `notebook.ipynb` (ne pas deplacer massivement vers une architecture package sans demande explicite).
- Conserver la logique de serie temporelle causale: aucun melange aleatoire entre passe et futur lors des splits.
- Pour toute comparaison d'architectures, reporter systematiquement MSE, MAE et RMSE (convention explicite README + notebook).
- Documenter les choix d'hyperparametres selon la trame scientifique du README (hypothese, methode, observations, conclusions).
- Style documentaire majoritairement francophone; rester coherent avec cette langue pour nouvelles explications markdown.

## Points d'integration / dependances externes
- Source de donnees: UCI "Individual household electric power consumption" (lien dans `README.md`).
- Librairies coeur:
  - `tensorflow==2.20.0`, `keras==3.10.0` pour modeles RNN,
  - `pandas==2.3.3` pour preparation,
  - `matplotlib==3.9.4`, `seaborn==0.13.2` pour visualisation.
- `.gitignore` exclut environnements, checkpoints notebook et artefacts de dev (`.venv/`, `.ipynb_checkpoints/`, `.idea/`).

## Quand un agent ajoute du code
- Privilegier des cellules notebook clairement nommees: chargement, preprocessing, modeles, evaluation.
- Si un helper `.py` est necessaire, le garder minimal et appeler depuis le notebook.
- Toujours inclure un bloc de comparaison final des 3 familles RNN avec tableau de metriques + graphe prediction vs reel.

