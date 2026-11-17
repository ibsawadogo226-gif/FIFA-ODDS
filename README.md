# FIFA Odds V2 — application web iPhone

Cette version remplace les cotes de démonstration qui changeaient au hasard par un outil d'analyse pédagogique basé sur des statistiques saisies ou importées.

## Fonctions
- Interface française adaptée à Safari et à l'écran d'accueil iPhone.
- Ajout de matchs et saisie des moyennes de buts marqués/encaissés.
- Estimation 1 / N / 2 avec un modèle de Poisson simple.
- Favoris, historique local, import JSON et export de sauvegarde.
- Aucune cote fictive et aucune actualisation aléatoire.

## Importer des matchs et statistiques
Le bouton « Importer JSON » accepte un tableau JSON ou un objet contenant `matches`. Chaque match doit avoir : `home`, `away`, `homeFor`, `homeAgainst`, `awayFor`, `awayAgainst`; `date` est facultatif.

Exemple de structure (les chiffres ci-dessous sont uniquement un exemple de format, pas des statistiques réelles) :

```json
{
  "matches": [
    {
      "home": "Equipe A",
      "away": "Equipe B",
      "date": "2026-11-10T18:00:00",
      "homeFor": 1.6,
      "homeAgainst": 0.9,
      "awayFor": 1.2,
      "awayAgainst": 1.4
    }
  ]
}
```

## Publier sur Netlify
1. Décompresser ce ZIP dans l'application Fichiers.
2. Ouvrir Netlify Drop dans Safari : https://app.netlify.com/drop
3. Choisir le dossier `fifa_odds_v2_work` (ou le dossier décompressé équivalent) avec « folder » / « choose a folder ».
4. Attendre la confirmation de publication.

## Limite importante
Cette version ne récupère pas encore automatiquement les vrais calendriers ni les statistiques des clubs. Pour cette fonction, il faudra choisir un fournisseur de données football, vérifier ses conditions et connecter une API via un backend sécurisé. Ne pas mettre une clé API secrète directement dans les fichiers publics du site.

Les probabilités sont des estimations mathématiques simplifiées, non des garanties de résultat.
