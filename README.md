# simpletd-site

Öffentliche Legal-/Support-Seiten für **SimpleTD** (App Store Connect).

| Seite | URL (nach Pages) | ASC-Feld |
|-------|------------------|----------|
| Support | `…/index.html` oder Site-Root | Support URL |
| Privacy | `…/privacy.html` | Privacy Policy URL |
| Impressum | `…/impressum.html` | (DE-Pflicht auf der Website) |

## Setup

1. Platzhalter ersetzen: `REPLACE_WITH_EMAIL`, Adresse, USt-Hinweis in den HTML-Dateien.
2. Public Repo auf GitHub (einmalig):

```bash
cd /Users/thomas/dev/simpletd-site
gh auth login   # falls nötig
gh repo create simpletd-site --public --source=. --remote=origin --push
gh api repos/tom4711/simpletd-site/pages -X POST -f build_type=legacy -f source[branch]=main -f source[path]=/
```

Erwartete Base-URL: `https://tom4711.github.io/simpletd-site/`

3. Optional als Submodule im privaten Game-Repo:

```bash
cd /Users/thomas/dev/SimpleTD
git submodule add https://github.com/tom4711/simpletd-site.git website
git commit -m "Add public legal site as submodule."
```

Site-Änderungen: im Submodule committen + pushen, danach im Parent den Submodule-Pointer committen.
