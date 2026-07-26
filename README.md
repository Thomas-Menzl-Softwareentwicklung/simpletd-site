# simpletd-site

Öffentliche Legal-/Support-Seiten für **SimpleTD** (App Store Connect).

| Seite | URL (nach Pages) | ASC-Feld |
|-------|------------------|----------|
| Support | `…/index.html` oder Site-Root | Support URL |
| Privacy | `…/privacy.html` | Privacy Policy URL |
| Impressum | `…/impressum.html` | (DE-Pflicht auf der Website) |

## Setup

1. Platzhalter ersetzen: `REPLACE_WITH_EMAIL`, Adresse, USt-Hinweis in den HTML-Dateien.
2. Public Repo auf GitHub (Org):

```bash
cd /Users/thomas/dev/simpletd-site
gh auth login   # falls nötig
# Repo liegt unter Thomas-Menzl-Softwareentwicklung/simpletd-site
gh api repos/Thomas-Menzl-Softwareentwicklung/simpletd-site/pages -X POST -f build_type=legacy -f source[branch]=main -f source[path]=/
```

Erwartete Base-URL: `https://thomas-menzl-softwareentwicklung.github.io/simpletd-site/`

3. Optional als Submodule im Game-Repo:

```bash
cd /Users/thomas/dev/SimpleTD
git submodule add https://github.com/Thomas-Menzl-Softwareentwicklung/simpletd-site.git website
git commit -m "Add public legal site as submodule."
```

Site-Änderungen: im Submodule committen + pushen, danach im Parent den Submodule-Pointer committen.
