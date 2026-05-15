# abasketcase.app — Site officiel

Site statique pour l'application mobile **A Basket Case**.

Hébergé sur GitHub Pages, domaine custom `abasketcase.app` via OVH.

## Pages

- `index.html` — Page d'accueil
- `privacy.html` — Politique de confidentialité (RGPD)
- `terms.html` — Conditions Générales d'Utilisation (CGU)

## Assets requis

Avant de pousser sur GitHub, vérifie que `assets/icon-1024.png` est bien présent.
C'est ton AppIcon (le même PNG que celui utilisé dans Xcode).

## Déploiement GitHub Pages

1. Créer un repo public sur GitHub (ex: `abasketcase-website`)
2. Push tous les fichiers à la racine
3. **Settings → Pages → Build from branch → main → /(root)** → Save
4. Attendre 1-2 minutes le premier déploiement
5. Le site sera accessible à `https://<username>.github.io/<repo-name>`

## Domaine custom (abasketcase.app)

### Étape 1 — Côté OVH (DNS)

Dans **OVH Manager → Domaines → abasketcase.app → Zone DNS**, ajouter :

```
Type    Sous-domaine    Cible
A       @               185.199.108.153
A       @               185.199.109.153
A       @               185.199.110.153
A       @               185.199.111.153
AAAA    @               2606:50c0:8000::153
AAAA    @               2606:50c0:8001::153
AAAA    @               2606:50c0:8002::153
AAAA    @               2606:50c0:8003::153
CNAME   www             <username>.github.io.
```

(remplace `<username>` par ton username GitHub réel)

### Étape 2 — Côté GitHub

1. Settings → Pages → Custom domain : entrer `abasketcase.app` → Save
2. Cocher "Enforce HTTPS" (apparaît après ~10-30 min, quand Let's Encrypt provisionne)

### Étape 3 — Vérification

Attendre 30 minutes (propagation DNS), puis ouvrir `https://abasketcase.app`.
Vérifier le cadenas vert (HTTPS), c'est obligatoire pour les `.app`.
