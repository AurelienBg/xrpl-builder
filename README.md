# XRPL Framework — Builder Suite

Suite complète d'outils pour **comprendre, idéer, valider et lancer** un projet sur le XRP Ledger (XRPL).

**Live site :** https://xrpl-builder.vercel.app

---

## Contenu

| # | Fichier | Type | Description |
|---|---------|------|-------------|
| 01 | `blockchain-framework-xrpl.html` | Statique | Anatomie de base : USER → CLIENT → CUSTODY → NETWORK → LEDGER |
| 02 | `blockchain-xrpl-extended.html` | Tour guidé | Anatomie complète + AMM/RWA/Sidechain · 9 étapes + play 5 cas |
| 03 | `blockchain-xrpl-animated.html` | Animé | Voyage d'une transaction · 3 scénarios |
| 04 | `builder-atlas.html` | Blueprints | 6 startup blueprints détaillés (RemitFlow, VaultDAO, BondBloc, MerchantPay, PropTok, PayrollXRP) |
| 05 | `cost-simulator.html` | Interactif | Comparateur live XRPL vs Stellar/Solana/Ethereum |
| 06 | `business-case-builder.html` | Interactif | Modélisation financière 24 mois (capex, opex, runway, breakeven) |
| 07 | `decision-tree.html` | Interactif | Arbre de décision technique guidé (4-6 questions → stack + boilerplate) |
| 08 | `decision-tree-map.html` | Statique | Vue macro complète de l'arbre · 19 chemins |
| 09 | `ecosystem-map.html` | Statique | Carte de l'écosystème XRPL mai 2026 · 50+ projets · opportunity gaps |
| -- | `blockchain-xrpl-extended.pdf` | PDF | Version imprimable A3 paysage de l'anatomie complète |

---

## Déploiement Vercel

### Méthode 1 — CLI (recommandée)

```bash
# Une seule fois : installer Vercel CLI
npm i -g vercel

# Dans ce dossier
cd /chemin/vers/xrpl-framework-site
vercel

# Suivre les prompts :
# - Set up and deploy ? Y
# - Which scope ? (ton compte)
# - Link to existing project ? N
# - Project name ? xrpl-builder
# - Directory ? ./ (Enter)
# - Override settings ? N

# Pour la production
vercel --prod
```

### Méthode 2 — GitHub + Vercel UI

1. Pusher ce dossier sur un repo GitHub (privé ou public)
2. Aller sur [vercel.com/new](https://vercel.com/new)
3. **Import Project** → choisir le repo
4. **Framework Preset** : Other (HTML statique détecté)
5. **Root Directory** : `./`
6. **Build Command** : laisser vide
7. **Output Directory** : laisser vide
8. **Deploy**

L'URL finale sera `xrpl-builder.vercel.app` (modifiable dans les settings du projet).

---

## URLs finales (clean URLs activé)

Une fois déployé, les URLs ressemblent à :

- `/` → page d'accueil (index.html)
- `/builder-atlas` → builder-atlas.html
- `/cost-simulator` → cost-simulator.html
- `/business-case-builder` → business-case-builder.html
- `/decision-tree` → decision-tree.html
- `/decision-tree-map` → decision-tree-map.html
- `/ecosystem-map` → ecosystem-map.html
- `/blockchain-framework-xrpl` → blockchain-framework-xrpl.html
- `/blockchain-xrpl-extended` → blockchain-xrpl-extended.html
- `/blockchain-xrpl-animated` → blockchain-xrpl-animated.html
- `/blockchain-xrpl-extended.pdf` → version PDF imprimable

---

## Développement local

```bash
# Méthode simple : python
python3 -m http.server 8000

# Ou via npm
npx serve .

# Ouvrir http://localhost:8000
```

Aucun build step nécessaire — c'est du HTML/CSS/JS statique pur.

---

## Maintenance

### Mettre à jour une page

Éditer le fichier HTML correspondant dans le dossier racine. Re-déployer avec `vercel --prod`.

### Mettre à jour l'Ecosystem Map

Le fichier `ecosystem-map.html` est conçu pour être édité manuellement. Chaque projet est un bloc `<div class="project">` indépendant (voir la section "À propos · maintenance manuelle" en bas de la page).

### Mettre à jour le Builder Atlas

Idem — chaque blueprint est une `<section class="startup">` autonome. Pour ajouter une fiche, dupliquer un bloc existant et modifier.

### Snapshot timestamp

L'Ecosystem Map est daté **mai 2026** — pense à mettre à jour la date dans le `<header>` lors d'une refresh trimestrielle.

---

## Stack technique

- HTML5 / CSS3 / Vanilla JavaScript
- Fonts : Fraunces (Google Fonts) + JetBrains Mono
- Aucun framework, aucune dépendance build
- Tous les SVG sont inline
- Compatible navigateurs modernes (Chrome, Firefox, Safari, Edge — dernières 2 versions)

## Architecture

Le projet est délibérément **multi-pages indépendantes** pour la phase v2.0. Pour une refonte avec composants partagés (design system unifié, navigation commune), voir le fichier `SPEC.md` (à venir si nécessaire).

---

## Licence

MIT — usage libre.
