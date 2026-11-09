# Notebook ventes et livraisons

## Exécution locale dans un éditeur

Le notebook utilise Python 3.11, Java 17 et Spark 3.5.7 en mode local.
Les calculs Spark s'exécutent sur le Mac et les données restent dans `data/`.
Le noyau `ipykernel` du venv permet d'exécuter les cellules dans un éditeur
compatible avec les notebooks, sans démarrer JupyterLab.

Depuis le dossier `Commandes`, pour recréer l'environnement :

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m ipykernel install --sys-prefix --name commandes --display-name "Python (Commandes .venv)"
```

Ouvrir `notebooks/exercice_livraisons.ipynb`, choisir le noyau
**Python (Commandes .venv)** ou l'interpréteur `.venv/bin/python`, puis exécuter
la cellule de démarrage Spark. Dans VS Code, utiliser **Sélectionner un noyau →
Environnements Python** ; les extensions Python et Jupyter permettent de lire
et d'exécuter le fichier `.ipynb`.

La cellule de démarrage fonctionne avec le répertoire courant à la racine du
projet ou dans `notebooks/`. Elle définit `DATA` et `RESULTATS` avec les chemins
locaux. La session utilise le fuseau horaire `Europe/Paris`. Sur macOS, Java 17
est sélectionné automatiquement. L'interface Spark est disponible sur
<http://localhost:4040> pendant l'exécution (ou un port suivant si déjà occupé).

Les conteneurs Spark et Jupyter ne sont pas nécessaires pour ce mode local.
Si MongoDB est utile pour la suite de l'exercice, démarrer uniquement ce service :

```bash
docker compose up -d mongo
```

Depuis le notebook local, son adresse est `mongodb://localhost:27017`.
Les sorties peuvent être écrites dans `resultats/`. Les cellules d'exercice
restent à compléter.
