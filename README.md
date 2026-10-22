# Checklist achat fourgon (PWA)

Application mobile hors-ligne pour contrôler un fourgon acheté à un particulier : cases à cocher (OK / problème), sauvegarde locale, export PDF. Aucune dépendance, aucun serveur.

## Publier sur GitHub Pages

1. Créer un dépôt GitHub (ex. `checklist-fourgon`), puis y déposer tous les fichiers de ce dossier à la racine.
2. Dépôt → **Settings → Pages** → *Source* : **Deploy from a branch** → branche `main`, dossier `/ (root)` → **Save**.
3. Après 1 à 2 minutes, l'app est en ligne sur `https://<ton-user>.github.io/checklist-fourgon/`.

En ligne de commande :

```bash
git init && git add . && git commit -m "Checklist fourgon PWA"
git branch -M main
git remote add origin https://github.com/<ton-user>/checklist-fourgon.git
git push -u origin main
```

## Installer sur le téléphone

- **Android (Chrome)** : menu ⋮ → *Installer l'application*.
- **iPhone (Safari)** : bouton Partager → *Sur l'écran d'accueil*.

Ouvrir l'app une fois avec du réseau : elle fonctionne ensuite sans connexion.

## Utilisation

- Touche une ligne : ☐ → ✔ OK → ✘ problème → ☐.
- Touche un titre de section pour la replier.
- Les infos du véhicule, les cases et les notes sont enregistrées sur le téléphone (localStorage).
- **Exporter en PDF** : ouvre la boîte d'impression, choisir *Enregistrer au format PDF*. Les problèmes (✘) apparaissent en gras.

## Mettre à jour

Modifier la checklist dans le tableau `DATA` de `index.html`, puis changer `CACHE = "fourgon-v1"` en `fourgon-v2` dans `sw.js` pour forcer le rafraîchissement.

Licence : MIT.
