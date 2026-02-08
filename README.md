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

## Updating PDF Versions

To ensure the downloadable PDF versions of the CV remain synchronized with the web content, follow these steps:

1. **Generate PDFs:** Use the following tool to convert the live URLs to PDF format: [PDF24 Web-to-PDF](https://tools.pdf24.org/es/sitio-web-a-pdf).
    
2. **URLs to Convert:**
    
    - **Spanish Version:** `https://isrengel.github.io/es/`
        
    - **English Version:** `https://isrengel.github.io/`
        
3. **Storage:** Once generated, download the files and place them in the following directory within the project:
    
    - `assets/pdf/`
        

By following this process, the downloadable assets will always reflect the latest updates made to the HTML version of the portfolio.