# DSS

## Anonymisation de données bancaires

Ce dépôt fournit un script Python permettant d'anonymiser des données sensibles
contenues dans un fichier CSV. Il remplace les informations personnelles
(nom, prénom, email, téléphone, adresse, IBAN, date de naissance) par des
valeurs fictives générées avec [Faker](https://faker.readthedocs.io/) et masque
les numéros de carte en conservant les quatre derniers chiffres.

### Prérequis
- Python 3.10+
- Dépendances : `pandas` et `faker`

Installez les dépendances avec :

```bash
pip install -r requirements.txt
```

### Utilisation

```bash
python anonymize_banking_data.py chemin/vers/source.csv chemin/vers/sortie.csv
```

Le script lit le CSV source, applique les règles d'anonymisation et écrit le
résultat dans le fichier de sortie indiqué.

### Notes
- Adaptez les noms de colonnes dans `SENSITIVE_FIELDS` si votre schéma diffère.
- Les adresses sont générées au format français et nettoyées pour rester sur
  une seule ligne.
- Les numéros de carte sont masqués : seuls les quatre derniers chiffres sont
  visibles.
