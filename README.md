# Transparency Portals Monorepo

This monorepo hosts three FY 2027 budget transparency portals, each powered by the public [BetterGov.ph Budget API](https://budget.bettergov.ph/docs):

1. **`apps/iriga`**: Iriga City, Camarines Sur (City portal)
2. **`apps/camsur`**: Province of Camarines Sur (Provincial portal)
3. **`apps/dpwh-camsur-district-5`**: Camarines Sur 5th District Engineering Office (DPWH DEO portal)

---

## Workspace Structure

```text
transparency-portal-iriga/
├── apps/
│   ├── iriga/                   # Iriga City portal
│   │   ├── portal.config.ts
│   │   ├── package.json
│   │   └── ...
│   ├── camsur/                  # Province of Camarines Sur portal
│   │   ├── portal.config.ts
│   │   ├── package.json
│   │   └── ...
│   └── dpwh-camsur-district-5/  # DPWH CamSur 5th DEO portal
│       ├── portal.config.ts
│       ├── package.json
│       └── ...
├── package.json                 # Monorepo root workspace config
└── tsconfig.json                # Project references
```

---

## Quickstart

Install dependencies across all workspaces:

```bash
npm install
```

### Run Locally

- **Iriga**: `npm run dev:iriga`
- **Camarines Sur**: `npm run dev:camsur`
- **DPWH CamSur District 5**: `npm run dev:dpwh`

### Check Portals against Live API

- **All**: `npm run check`
- **Iriga**: `npm run check:iriga`
- **Camarines Sur**: `npm run check:camsur`
- **DPWH CamSur District 5**: `npm run check:dpwh`

### Build

- **Build all**: `npm run build`
- **Build Iriga**: `npm run build:iriga`
- **Build Camarines Sur**: `npm run build:camsur`
- **Build DPWH CamSur District 5**: `npm run build:dpwh`

### Lint

```bash
npm run lint
```

---

## Deploying to Vercel

All three portals can be deployed from this single `monorepo` branch into separate Vercel projects:

### 1. Iriga City Portal
- **Import Project** in Vercel from this repository.
- **Git Branch**: `monorepo`
- **Root Directory**: `apps/iriga`
- **Framework Preset**: Vite (detected automatically)
- **Build Command**: `npm run build`
- **Output Directory**: `dist`

### 2. Province of Camarines Sur Portal
- **Add New Project** in Vercel from the same repository.
- **Git Branch**: `monorepo`
- **Root Directory**: `apps/camsur`
- **Framework Preset**: Vite
- **Build Command**: `npm run build`
- **Output Directory**: `dist`

### 3. DPWH CamSur District 5 Portal
- **Add New Project** in Vercel from the same repository.
- **Git Branch**: `monorepo`
- **Root Directory**: `apps/dpwh-camsur-district-5`
- **Framework Preset**: Vite
- **Build Command**: `npm run build`
- **Output Directory**: `dist`
