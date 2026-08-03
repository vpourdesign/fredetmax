# Dashboard stats — Fred et Max · état de l'install

Installé le **2026-06-14** par le skill `install-tool` (blueprint `_AGENCY/CTO/blueprints/seo-stats-dashboard/`).

## ✅ Déjà fait (automatique)

- Fichiers de l'outil copiés ici (Next.js 14 + Tailwind + recharts).
- `META_AD_ACCOUNT_ID=act_129396217452544` — auto depuis le registre `_AGENCY/CTO/integrations/meta-ads-accounts.json`.
- `GOOGLE_SERVICE_ACCOUNT_KEY` + `DASHBOARD_PASSWORD` — réutilisés depuis le coffre `_AGENCY/.vault/` (non affichés).

- `GSC_SITE_URL=sc-domain:fredetmax.com` — rempli le 2026-08-03. Propriété de domaine
  confirmée : elle couvre `www.fredetmax.com` + les 4 sous-domaines des landing pages
  (`lorraine`, `rosemere`, `blainville`, `stetherese`), tous avec sitemap déclaré.

## ⛔ Ce qui manque pour que ça tourne

**1. Une valeur à me donner** (je finalise le `.env.local` ensuite) :

| Clé | C'est quoi | Où la trouver |
|---|---|---|
| `GA4_PROPERTY_ID` | ID **numérique** de la propriété GA4 (≠ `G-FHDWV9DP9N`, qui est l'ID de mesure) | GA4 → Admin → Paramètres de la propriété → « ID de la propriété » |

**2. Donner accès au service account côté Google** (sinon les API renvoient vide) :

- **GA4** → Admin → Accès à la propriété → ajouter `rapportsvpd@site-vpd.iam.gserviceaccount.com` en **Lecteur**.
- **Search Console** → Paramètres → Utilisateurs et autorisations → ajouter le même compte en **Lecteur**.

**3. Installer les dépendances + lancer :**
```bash
cd FREDETMAX/06_livrables/dashboard-stats
npm install
npm run dev
```

## Comment me le rappeler / relancer

Dis simplement : **« finis le dashboard stats de Fred et Max »** (ou « installe le dashboard stats dans Fred et Max »). Je lirai ce fichier, je te redemanderai les 2 valeurs manquantes et je terminerai.
