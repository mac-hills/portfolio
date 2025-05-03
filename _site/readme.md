# Portfolio Website

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-brightgreen)](https://mac-hills.github.io/portfolio/)

Static site built with Jekyll and deployed to GitHub Pages.

## Manual Deployment to GitHub Pages

### Prerequisites
- Ruby (with Jekyll and Bundler installed)
- Git

### Deployment Steps

1. **Build the site**  
   Generate static files in `_site` directory:
   ```bash
   bundle exec jekyll build
   ```

2. **Add built files to Git**  
   Force-add the generated files (ignores .gitignore rules):
   ```bash
   git add _site -f
   git commit -m "Add built files for deployment"
   ```

3. **Push to gh-pages branch**  
   Deploy using git subtree:
   ```bash
   git subtree push --prefix _site origin gh-pages
   ```

### Post-Deployment
- Site will be live at:  
  `https://mac-hills.github.io/portfolio/`
- Check deployment status in GitHub:  
  `Repository → Actions → Pages build and deployment`

---

## Development Setup

1. Install dependencies:
   ```bash
   bundle install
   ```

2. Run local server:
   ```bash
   bundle exec jekyll serve
   ```
   Visit `http://localhost:4000/portfolio/`

---

## Troubleshooting

- **404 Errors**:  
  Add empty `.nojekyll` file to root directory
  ```bash
   touch .nojekyll
   ```

- **Outdated Content**:  
  Clear browser cache with `Ctrl + F5`/`Cmd + Shift + R`

- **Path Issues**:  
  Ensure `_config.yml` has:
  ```yaml
  baseurl: "/portfolio"
  url: "https://mac-hills.github.io"
  ```

---

**Note**: Never manually modify files in the `_site` directory - they get regenerated on build.

Tested on Jekyll v4.2.0
```