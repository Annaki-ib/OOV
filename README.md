
```markdown
# POS & Morph Tagging pour le Français et le Dialecte Algérien

Ce projet vise à entraîner et évaluer des taggers morpho-syntaxiques (POS Tagging) et morphologiques (par exemple, le trait *Number*) sur deux langues :
- Le français, via des corpus UD (Universal Dependencies).
- Un dialecte algérien, également sous forme de fichiers UD (Universal Dependencies) Mélange de français anglais arabe écrite en Français.

## Structure du dépôt

```
your-project/

├── README.md                      # Description générale du projet (ce fichier)

├── requirements.txt               # Liste des dépendances Python

├── French/                        # Corpus UD en français

│   ├── fr_partut-ud-train.conllu

│   ├── fr_partut-ud-dev.conllu

│   └── fr_partut-ud-test.conllu

├── algerian_dialect/             # Corpus UD pour le dialecte algérien

│   ├── qaf_arabizi-ud-train.conllu

│   ├── qaf_arabizi-ud-dev.conllu

│   └── qaf_arabizi-ud-test.conllu

├── notebooks/                     # Notebooks Jupyter d'entraînement et d'évaluation

│   ├── algeria/

│   │   ├── TP1qaf.ipynb          # Notebooks spécifiques au dialecte algérien

│   │   └── TP3qaf.ipynb

│   └── French/

│       ├── TP1_POSTAG.ipynb      # Notebooks spécifiques au français

│       └── TP3.ipynb

├── outputs/                       # Résultats (modèles entraînés, prédictions)

│   ├── AQF/

│   │   ├── TP1/

│   │   └── TP3/

│   └── French/

│       ├── TP1/

│       └── TP3/

├── src/                           # Scripts Python réutilisables

│   ├── accuracy.py               # Script pour calculer l'accuracy et autres scores

│   ├── conllulib.py             # Fonctions utilitaires pour manipuler du CoNLL-U

│   └── ...

└── tests/                         # Dossier pour les tests des pistes
    └── ... 
    
```

## Installation

1. Cloner ce dépôt :  
   ```bash
   git clone https://github.com/mon-compte/your-project.git
   cd your-project
   ```

2. Installer les dépendances:  
   ```bash
   pip install -r requirements.txt
   ```
   Assurez-vous que `requirements.txt` contient toutes les bibliothèques nécessaires (PyTorch, conllu, scikit-learn, etc.).

## Utilisation

### 1. Données
- Placez les fichiers `.conllu` du **français** dans le dossier `French/`.
- Placez les fichiers `.conllu` du **dialecte algérien** dans le dossier `algerian_dialect/`.

### 2. Notebooks
- Les notebooks d’entraînement et d’évaluation pour le français se trouvent dans `notebooks/French/`.
- Ceux pour le dialecte algérien se trouvent dans `notebooks/algeria/`.

Ouvrez-les dans Jupyter (ou JupyterLab) et exécutez-les dans l’ordre indiqué (par exemple TP1, puis TP3) pour entraîner et évaluer vos modèles.

### 3. Scripts Python
- Les scripts réutilisables (ex. `accuracy.py`, `conllulib.py`) sont dans `src/`.
- Vous pouvez importer ces scripts dans vos notebooks en ajustant votre `sys.path` ou en utilisant une installation locale.

### 4. Exemples de commandes
- **Évaluation avec `accuracy.py`** (pour le français, par exemple) :
  ```bash
  python src/accuracy.py \
      -p outputs/French/TP1/pred.conllu \
      -g French/fr_partut-ud-test.conllu \
      -t French/fr_partut-ud-train.conllu \
      -c upos \
      -f form
  ```
  Cela va calculer l’accuracy UPOS (ou autre colonne selon l’option `-c`) .

## Jeux de données

- Les fichiers UD pour le **français** proviennent par exemple de [Universal Dependencies](https://universaldependencies.org/) (UD_French-*Partut*).
- Les fichiers UD pour le **dialecte algérien** proviennent de[Universal Dependencies](https://universaldependencies.org/) .

## Résultats et modèles

- Les modèles entraînés (`.pt`) et les prédictions (`pred.conllu`) sont enregistrés dans `outputs/`.
- Vous pouvez retrouver les fichiers de vocabulaire (`vocab_words.txt`, `vocab_pos.txt`, etc.) dans les mêmes dossiers, selon votre organisation.



## Contributeurs

- ANNAKI Ibtihal / CHAKIR Oussama


