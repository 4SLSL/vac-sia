# vac-sia — Module SIA / VAC pour X-Dispatch

Module communautaire pour X-Plane 12 : cartes **VAC** françaises (eAIP SIA), aperçu intégré dans l’app, fond **OACI** (MBTiles + espaces aériens).

Compatible avec [X-Dispatch](https://github.com/lyestarzalt/x-dispatch) **≥ 1.9.2** (fork intégré : [4SLSL/x-dispatch](https://github.com/4SLSL/x-dispatch)).

**v1.1.0** : onglet Réglages dédié, import VAC international (ZIP/dossier), retrait des fonds OACI.

## Installation

Dans X-Dispatch : **Réglages → Modules**

- Activer **SIA France Charts** (version fournie avec le fork 4SLSL), ou
- **Installer depuis GitHub** : `4SLSL/vac-sia` (release ZIP), ou
- **Installer depuis ZIP** : archive contenant `x-dispatch-module.json` à la racine

## Structure du dépôt

| Dossier | Rôle |
|---------|------|
| `x-dispatch-module.json` | Manifeste module (schéma phase 1) |
| `src/lib/` | Logique métier SIA (eAIP, index VAC, téléchargement, PDF) |
| `src/main/` | IPC Electron, protocole `vac-pdf://`, cycle de vie |
| `src/renderer/` | Points d’entrée renderer (wrappers vers l’app hôte) |
| `host-ui/` | Composants React et hooks à intégrer dans `x-dispatch` (`registry.tsx`) |

Le module **s’exécute dans le processus X-Dispatch** : `host-ui/` et une partie de `src/main/` utilisent des APIs du core (`@/lib/db`, `@/main/pdfCapture`, etc.). Ce dépôt est la **source canonique** du plugin ; le fork 4SLSL l’embarque sous `src/modules/sia-france/`.

## Développement

1. Modifier ce dépôt (`vac-sia`).
2. Synchroniser vers `x-dispatch` : copier `src/lib`, `src/main`, `host-ui` vers les chemins documentés dans [INTEGRATION.md](./INTEGRATION.md).
3. Tester avec `npm run dev` dans x-dispatch.

## Données & légal

Données © **SIA/DGAC** — usage navigation VFR. Compte gratuit requis sur [sia.aviation-civile.gouv.fr](https://www.sia.aviation-civile.gouv.fr) pour les téléchargements eAIP.

## Licence

GPL-3.0-only — alignée sur X-Dispatch.
