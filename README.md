# patgmac-recipes

AutoPkg recipes for macOS software packaging and Munki imports.

## About

This repository contains download, pkg, install, and munki recipes for several vendors. These recipes are intended for AutoPkg workflows used by Mac admins.

## Requirements

- AutoPkg installed and working
- For `.munki.recipe` files: a configured Munki repo
- For `Netskope-Win.download.recipe`: `com.github.hansen-m.SharedProcessors/MSIInfoVersionProvider`

## Add This Repo to AutoPkg

```bash
autopkg repo-add https://github.com/patgmac/patgmac-recipes.git
autopkg repo-update all
```

## Recipe Catalog

### CrystalMaker

- `CrystalMaker/CrystalMaker.download.recipe`
- `CrystalMaker/CrystalMaker.pkg.recipe`
- `CrystalMaker/CrystalDiffract.download.recipe`
- `CrystalMaker/CrystalDiffract.pkg.recipe`
- `CrystalMaker/SingleCrystal.download.recipe`
- `CrystalMaker/SingleCrystal.pkg.recipe`

Notes:
- CrystalMaker-family download recipes currently fetch the latest available release each run.
- The recipe then derives version information after download.

### Netskope

- `Netskope/Netskope.download.recipe` (macOS)
- `Netskope/Netskope-Win.download.recipe` (Windows installer download + MSI version)
- `Netskope/Netskope.munki.recipe`

**Required Configuration:**
These recipes download the Netskope client directly from your organization's Netskope tenant. You must provide your tenant's download hostname.

Notes:
- Set `HOSTNAME` to your tenant's download host (for example `download-company.goskope.com`).
- Contact your Netskope administrator if you don't know your tenant hostname.
- `Netskope.munki.recipe` inherits from the macOS download recipe.

### Palo Alto Networks

- `PaloAltoNetworks/PrismaAccessBrowserPKG.download.recipe`
- `PaloAltoNetworks/PrismaAccessBrowserPKG.pkg.recipe`
- `PaloAltoNetworks/PrismaAccessBrowserPKG.munki.recipe`

Notes:
- Recipes use a Sparkle feed to locate current Prisma Access Browser packages.
- For non-pkg recipes (e.g., direct munki import without pkg creation), see [erikng-recipes](https://github.com/autopkg/erikng-recipes/tree/main/PaloAltoNetworks).

### Volitans Software

- `Volitans Software/SMART Utility.download.recipe`
- `Volitans Software/SMART Utility.pkg.recipe`
- `Volitans Software/SMART Utility.install.recipe`

Notes:
- **Deprecated.** Use [flammable-recipes](https://github.com/grahampugh/flammable-recipes) instead.

## Typical Usage

Run a recipe directly:

```bash
autopkg run -v com.github.patgmac.pkg.CrystalMaker
```

Use an override file (recommended):

```bash
autopkg make-override com.github.patgmac.munki.Netskope
autopkg edit override.munki.Netskope.recipe
autopkg run -v override.munki.Netskope.recipe
```

## Useful Override Example

For Netskope, set your tenant hostname in your override:

```xml
<key>HOSTNAME</key>
<string>your-tenant.goskope.com</string>
```

## Contributing

Issues and pull requests are welcome, especially for:

- Signature updates
- URL/appcast changes
- Munki metadata improvements
- New recipe additions
