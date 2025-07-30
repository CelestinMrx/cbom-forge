# Forger un CBOM

## Étape 1 : Récupérer les fichiers d’analyse

1. Créez un dépôt GitHub nommé **cbom-forge** pour y stocker le code.
2. Depuis le dépôt [cbom-action](https://github.com/advanced-security/cbom-action), copiez dans ce nouveau dépôt les dossiers suivants :
   - `analyse`
   - `build-matrix`
   - `workflow-summary`
3. Ouvrez le fichier `analyse/action.yml` et remplacez toutes les occurrences de `v3` par `v4` afin d'assurer la compatibilité avec les versions récentes de GitHub Actions.

## Étape 2 : Forger un CBOM

1. Activez **CodeQL** :
   - Allez dans l’onglet **Settings** de votre dépôt.
   - Ouvrez la section **Advanced Security**.
   - Cliquez sur **Set up** dans la ligne correspondant à **CodeQL** et choisissez l’option **Default**.

2. Depuis le dépôt [cbom-action](https://github.com/advanced-security/cbom-action), copiez le dossier `.github`, qui contient :
   - un sous-dossier `workflows` avec un fichier `.yml` à l’intérieur.

3. Dans ce fichier `.yml`, remplacez toutes les occurrences de :
```
advanced-security/cbom-action
```
par:
```
<nom_utilisateur>/cbom-forge
```

4. Une fois les modifications commitées, allez dans l’onglet **Actions** de votre dépôt :
- Cliquez sur **Create Crypto Bill of Materials**.
- Cliquez ensuite sur **Run**.

5. Une fois le workflow terminé, un résumé du CBOM devrait apparaître en dessous.
