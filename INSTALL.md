# Installation & Deployment Guide

**Tonuino Card Creator** is a zero-dependency, single-file HTML application. It requires no backend server, database, or build tools.

Below are the common ways to run or host the application.

---

## Option 1: Local Usage (No Server Needed)

1. Clone or download the repository:
   ```bash
   git clone [https://github.com/cnlpete/tonuino-card-creator.git](https://github.com/cnlpete/tonuino-card-creator.git)
   cd tonuino-card-creator
   ```
2. Double-click `index.html` or open it directly in your web browser:
   ```bash
   # On Linux
   xdg-open index.html

   # On macOS
   open index.html
   ```

---

## Option 2: GitHub Pages (Recommended for Free Cloud Hosting)

Live Demo: [https://cnlpete.github.io/tonuino-card-creator/](https://cnlpete.github.io/tonuino-card-creator/)

1. Push this repository to your GitHub account (e.g. `cnlpete/tonuino-card-creator`).
2. Go to **Settings** > **Pages** in your GitHub repository.
3. Under **Build and deployment**:
   - **Source**: Select `GitHub Actions`.
4. On every push to `master`, the workflow automatically tags the release and deploys to GitHub Pages.

---

## Option 3: GitLab Pages

1. Create a `.gitlab-ci.yml` file in the repository root with the following content:

   ```yaml
   pages:
     stage: deploy
     script:
       - mkdir .public
       - cp index.html .public/
       - mv .public public
     artifacts:
       paths:
         - public
     only:
       - main
   ```

2. Push to GitLab. Your page will automatically build and deploy under GitLab Pages.

---

## Option 4: Static Web Server / Nginx / Docker

### Using Nginx (Static)
Copy `index.html` to your server's document root (e.g., `/var/www/html/index.html`).

### Using Docker (Nginx Alpine)
Run a quick static web server container:

```bash
docker run -d \
  --name tonuino-card-creator \
  -p 8080:80 \
  -v $(pwd)/index.html:/usr/share/nginx/html/index.html:ro \
  nginx:alpine
```

Access the app at `http://localhost:8080`.