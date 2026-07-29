# simpletd-site

Öffentliche Legal-/Support-Seiten für **SimpleTD** (App Store Connect).

| Seite | URL (nach Pages) | ASC-Feld |
|-------|------------------|----------|
| Support (DE) | `…/index.html` oder Site-Root | Support URL |
| Privacy (DE) | `…/privacy.html` | Privacy Policy URL |
| Impressum (DE) | `…/impressum.html` | (DE-Pflicht auf der Website) |
| Support (EN) | `…/en/index.html` | optional |
| Privacy (EN) | `…/en/privacy.html` | optional |
| Legal Notice (EN) | `…/en/impressum.html` | — |

Sprachumschalter **DE · EN** in der Navigation. Deutsch bleibt die Startseite; Englisch liegt unter `/en/`.

## Setup

1. Public Repo auf GitHub (Org):

```bash
cd /Users/thomas/dev/simpletd-site
gh auth login   # falls nötig
# Repo liegt unter Thomas-Menzl-Softwareentwicklung/simpletd-site
gh api repos/Thomas-Menzl-Softwareentwicklung/simpletd-site/pages -X POST -f build_type=legacy -f source[branch]=main -f source[path]=/
```

Erwartete Base-URL: `https://thomas-menzl-softwareentwicklung.github.io/simpletd-site/`

2. Optional als Submodule im Game-Repo:

```bash
cd /Users/thomas/dev/SimpleTD
git submodule add https://github.com/Thomas-Menzl-Softwareentwicklung/simpletd-site.git website
git commit -m "Add public legal site as submodule."
```

Site-Änderungen: im Submodule committen + pushen, danach im Parent den Submodule-Pointer committen.
