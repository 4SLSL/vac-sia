# Intégration dans x-dispatch

Chemins cibles dans le dépôt [4SLSL/x-dispatch](https://github.com/4SLSL/x-dispatch) :

| Source (`vac-sia`) | Cible (`x-dispatch`) |
|--------------------|----------------------|
| `src/lib/*` | `src/modules/sia-france/lib/*` |
| `src/main/*` | `src/modules/sia-france/main/*` |
| `host-ui/airport/*` | `src/components/layout/AirportInfoPanel/tabs/*` |
| `host-ui/settings/SiaChartsSection.tsx` | `src/components/dialogs/SettingsDialog/sections/SiaChartsSection.tsx` |
| `host-ui/hooks/*` | `src/components/Map/hooks/*` |
| `host-ui/SiaUpdateBanner.tsx` | `src/components/SiaUpdateBanner.tsx` |
| `host-ui/queries/useSiaQuery.ts` | `src/queries/useSiaQuery.ts` |

Enregistrement app :

- `initModuleManager([siaFranceManifest])` dans `src/main.ts`
- Entrées `sia-france` dans `src/lib/modules/registry.tsx`
- Catalogue : `registry/modules.json` → `"repository": "4SLSL/vac-sia"`
