# 🧠 AI BET E-GO

> **La data au service de vos paris.** Coupons de pronostics sportifs générés avec assistance IA, analyses de matchs et statistiques avancées.

[![Vercel](https://img.shields.io/badge/Vercel-Live-2ce458?style=flat-square&logo=vercel&logoColor=white)](https://ai-bet-ego-hwi-qen.vercel.app)
[![HTML5](https://img.shields.io/badge/HTML5-Vanilla-E34F26?style=flat-square&logo=html5&logoColor=white)](index.html)
[![CSS3](https://img.shields.io/badge/CSS3-Pure-1572B6?style=flat-square&logo=css3&logoColor=white)](index.html)
[![License](https://img.shields.io/badge/Licence-Tous%20droits%20réservés-9db0a2?style=flat-square)](./index.html)

---

## 🌐 Démo live

🔗 **[https://ai-bet-ego-hwi-qen.vercel.app](https://ai-bet-ego-hwi-qen.vercel.app)**

---

## 📋 Présentation

**AI BET E-GO** est une landing page de pronostics sportifs assistés par IA. Le site présente un service de coupons de paris générés chaque jour, distribués via une chaîne WhatsApp. Il s'agit d'un **site vitrine statique** — HTML/CSS/JS pur, sans framework ni backend.

### Chiffres mis en avant

| Métrique | Valeur |
|----------|--------|
| Cote combinée record | **~548x** |
| Sélections max / coupon | **12** |
| Matchs analysés / an | **1 250+** |
| Disponibilité IA | **24/7** |

---

## 🗂️ Structure du site

Le site est composé d'un **fichier unique** (`index.html`, ~77 Ko) regroupant 15 sections :

| # | Section | ID | Description |
|---|---------|-----|-------------|
| 1 | **Hero** | — | Pitch principal, mini-ticket animé, stats clés, chips flottants |
| 2 | **Ticker** | — | Marquee défilant : ANALYSE · PRONOSTICS · GAIN · IA |
| 3 | **Fonctionnalités** | `#fonctionnalites` | Grille de 7 features cards |
| 4 | **Manifesto** | — | Section fond photo parallax + texte animé ligne par ligne |
| 5 | **Coupon du jour** | `#coupon` | Ticket complet : tableau de 6 sélections (+ 6 sur WhatsApp), stats, exemple de gain |
| 6 | **Analyse IA** | `#analyse` | 4 étapes du processus + card d'exemple Argentina vs Bolivia |
| 7 | **Stats Band** | — | 4 compteurs animés au scroll |
| 8 | **Gains récents** | `#gains` | 3 cards de coupons gagnants en rotation CSS |
| 9 | **Galerie** | `#galerie` | 9 cards d'historique filtrables (HIGH ODDS / SÉCURISÉ / LAB IA) |
| 10 | **Types de coupons** | `#types` | 3 profils de risque avec jauge visuelle |
| 11 | **Avis** | `#avis` | 2 rangées de témoignages en défilement CSS infini |
| 12 | **Programme** | `#programme` | 5 prochains matchs analysés avec badges statut |
| 13 | **FAQ** | `#faq` | 5 accordéons natifs `<details>/<summary>` |
| 14 | **CTA WhatsApp** | `#rejoindre` | Card dégradé avec bouton d'inscription |
| 15 | **Footer** | — | Navigation, newsletter (simulée), avertissement jeu responsable |

---

## ⚙️ Stack technique

### Technologies

| Couche | Détail |
|--------|--------|
| **HTML5** | Sémantique (`<header>`, `<main>`, `<section>`, `<footer>`, `<article>`, `<details>`) |
| **CSS3** | Custom properties, Grid, Flexbox, `clamp()`, `min()`, `env(safe-area-inset-*)`, `backdrop-filter`, `mask-image` |
| **JavaScript** | Vanilla ES6+ — Intersection Observer API, `requestAnimationFrame`, event delegation |
| **Polices** | Google Fonts : **Space Grotesk** (titres) + **Inter** (corps de texte) |
| **Icônes** | SVG inline avec sprite technique (`<symbol>` + `<use href>`) — aucune dépendance externe |

### JavaScript — fonctionnalités

```
Navbar         → Effet blur + changement de couleur au défilement
Menu burger    → Toggle mobile avec gestion aria-expanded
Scroll reveal  → IntersectionObserver : opacité + translateY sur entrée dans le viewport
Compteurs      → IntersectionObserver + requestAnimationFrame, easing cubique (ease-out)
Galerie        → Filtrage dynamique avec animation galIn (scale + translateY)
Newsletter     → Simulation de soumission de formulaire (hide/show)
```

### Design system

```css
/* Couleurs principales */
--bg:        #070a08   /* Fond principal */
--bg-2:      #0b100c   /* Fond secondaire */
--card:      #0e1510   /* Surfaces de cards */
--green:     #2ce458   /* Accent principal */
--text:      #f2f5f2   /* Texte principal */
--muted:     #9db0a2   /* Texte secondaire */

/* Typographie */
--display:   "Space Grotesk"  /* H1, H2, H3, chiffres */
--body:      "Inter"          /* Paragraphes, labels */

/* Formes */
--radius:    22px             /* Border-radius global */
```

### Animations CSS

| Nom | Usage |
|-----|-------|
| `float` | Chips flottants hero (translateY loop) |
| `pulse` | Point vivant dans la pill hero |
| `scrollX` | Ticker marquee gauche (rangée 1) |
| `scrollXrev` | Ticker marquee droite (rangée 2 avis) |
| `galIn` | Apparition des cards filtrées (scale + translateY) |

---

## 📱 Responsive

Breakpoints définis en CSS (mobile-first adapté) :

| Breakpoint | Changements |
|------------|------------|
| `≤ 1024px` | Menu burger actif, grille hero 1 colonne |
| `≤ 1000px` | Grilles feat/types/wins en 1 colonne, `.a-card` statique |
| `≤ 760px` | Animation burger active (X), review cards plus étroites |
| `≤ 640px` | Feat-grid 1 colonne, stats hero en colonne, galerie 1 colonne |
| `≤ 520px` | Métadonnées ticket en 1 colonne, logo réduit |
| `≤ 480px` | CTAs hero pleine largeur, chips compacts |

Support iOS : `viewport-fit=cover` + `env(safe-area-inset-top/bottom)` pour les notchs et barres système.

---

## ♿ Accessibilité

- `aria-hidden="true"` sur tous les éléments décoratifs (marquee, code-barres, watermark)
- `aria-label` sur les boutons icône (burger, réseaux sociaux)
- `aria-expanded` géré dynamiquement sur le menu burger
- `rel="noopener"` sur tous les liens `target="_blank"`
- FAQ en `<details>/<summary>` natif — 0 JS, accessible nativement
- `scroll-margin-top: 110px` sur chaque `<section>` pour compenser la navbar fixe

---

## 🚀 Déploiement

```
Hébergement  →  Vercel (team : hwi-qen)
Repo         →  GitHub : Hwi-Qui/ai-bet-e-go
Branche prod →  main
Auto-deploy  →  Actif — chaque push sur main redéploie automatiquement
Build        →  Aucun (fichier statique, Vercel sert index.html directement)
```

### Déployer localement

```bash
# Aucune dépendance — ouvrir directement dans un navigateur
open index.html

# Ou via un serveur local (recommandé pour les fonts)
npx serve .
# → http://localhost:3000
```

---

## 📂 Arborescence du repo

```
ai-bet-e-go/
├── index.html      # Site complet (HTML + CSS + JS inline, ~77 Ko)
└── README.md       # Ce fichier
```

---

## 🔗 Canal WhatsApp

Les coupons du jour sont publiés gratuitement chaque matin sur la chaîne officielle :

👉 **[whatsapp.com/channel/0029VbE4mUzCHDynH0pRA02W](https://whatsapp.com/channel/0029VbE4mUzCHDynH0pRA02W)**

---

## ⚠️ Avertissement

> Les pronostics sont fournis **à titre informatif uniquement** et ne garantissent aucun gain. Le jeu comporte des risques : endettement, isolement, dépendance. **Jouez de manière responsable.** Besoin d'aide ? **09 74 75 13 13** (appel non surtaxé). Réservé aux **18 ans et plus.**

---

## 📄 Licence

© 2026 **AI BET E-GO** — Tous droits réservés.  
Conçu avec l'assistance IA.
