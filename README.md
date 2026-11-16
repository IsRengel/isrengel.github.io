# My Hugo Portfolio - Interactive CV

This repository contains the source code for my professional portfolio and CV, built using the Hugo static site generator. The site is designed with full multilingual support, offering complete versions in both **English** and **Spanish**.

---

## Getting Started

### Local Development

To run the project locally for development and previewing changes, ensure you have Hugo installed on your system. Run the following command in the root directory:

```bash
hugo server
```

The site will be available at `http://localhost:1313/`. This mode includes live reloading, so any changes made to the content or configuration will be reflected instantly in the browser.

### Configuration

All global settings, including menu structures, social media links, and multilingual parameters, are managed through the central configuration file:

- `config.toml`
    

---

## Deployment

The deployment process is fully automated. This repository utilizes **GitHub Actions** to handle the build and hosting processes.

- **Production:** To update the live site, simply push or merge your changes into the `main` branch.
    
- **Automation:** The workflow will automatically trigger, compile the static files using Hugo, and deploy them to GitHub Pages.
    

---

## PDF Versions

The downloadable PDFs are **generated automatically on every deploy** — there is nothing to do by hand, and they can never drift from the HTML.

During the GitHub Actions run, the workflow builds a second copy of the site pointed at `localhost`, serves it, and prints both language versions to PDF with headless Chrome:

- `assets/pdf/cv_en.pdf` ← `/`
- `assets/pdf/cv_es.pdf` ← `/es/`

If either file fails to render, the workflow fails and nothing is deployed, so the live download links never point at a broken file.

Because of this, the PDFs are **not committed to the repository** (they are listed in `.gitignore`). They only exist in the deployed output. To preview them locally:

```bash
hugo --minify --baseURL "http://localhost:8099/" -d ./pdfsrc
python3 -m http.server 8099 --directory ./pdfsrc &
google-chrome --headless --no-pdf-header-footer --virtual-time-budget=20000 \
  --print-to-pdf=cv_en.pdf http://localhost:8099/
```

Note that a plain `hugo server` will 404 on the CV download links, since the files are produced only at deploy time.