README.md
# MyApp - React + Azure Static Web App

This is a **React** project deployed as an **Azure Static Web App** using **GitHub Actions** for CI/CD. Every push to the `main` branch automatically builds and deploys the app.

---

## Table of Contents

1. [Project Structure](#project-structure)
2. [Getting Started](#getting-started)
3. [Build & Run Locally](#build--run-locally)
4. [GitHub Actions Deployment](#github-actions-deployment)
5. [Azure Static Web App Deployment](#azure-static-web-app-deployment)
6. [License](#license)

---

## Project Structure



myapp/
├─ build/ # Build output (generated)
├─ node_modules/
├─ public/
├─ src/
├─ package.json
├─ package-lock.json
├─ .gitignore
└─ .github/workflows/
└─ azure-static-web-app.yml # GitHub Actions workflow


---

## Getting Started

### Prerequisites

- Node.js v20.x
- npm v10.x
- Git
- Azure account
- GitHub account

### Clone repository

```bash
git clone https://github.com/<your-username>/myapp.git
cd myapp

Build & Run Locally

Install dependencies:

npm install


Run the development server:

npm start


Open your browser:

http://localhost:3000


Create production build:

npm run build


The optimized build will be in the build/ folder.

GitHub Actions Deployment

This project uses GitHub Actions to automate deployment to Azure Static Web Apps:

Workflow file: .github/workflows/azure-static-web-app.yml

Trigger: Push to main branch

Steps:

Checkout repo

Set up Node.js environment

Install dependencies

Build React app

Deploy build/ folder to Azure Static Web App

Deployment Token

Create a secret in GitHub: AZURE_STATIC_WEB_APPS_API_TOKEN

Get the token from Azure Portal → Your Static Web App → Deployment Center → GitHub Actions → Generate token

Azure Static Web App Deployment

Create a Static Web App in Azure.

Choose GitHub as the source.

Set Build Configuration:

App location: /

Output location: build

The app will deploy automatically via GitHub Actions.

Visit the Azure-provided URL to see your live app.

License

This project is licensed under the MIT License.


---

# Step-by-Step Deployment Guide

### 1️⃣ Set up the React project

```bash
npx create-react-app myapp
cd myapp


Add your app code.

Test locally with npm start.

2️⃣ Build for production
npm run build


This generates the build/ folder ready for deployment.

3️⃣ Create GitHub repository

Push your code to GitHub:

git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<username>/myapp.git
git push -u origin main

4️⃣ Configure GitHub Actions for deployment

Create folder: .github/workflows/

Add file: azure-static-web-app.yml

Paste workflow:

name: Azure Static Web App CI/CD

on:
  push:
    branches:
      - main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-node@v3
      with:
        node-version: '20'
    - run: npm install
    - run: npm run build
    - uses: Azure/static-web-apps-deploy@v1
      with:
        azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN }}
        repo_token: ${{ secrets.GITHUB_TOKEN }}
        action: "upload"
        app_location: "/"
        output_location: "build"

5️⃣ Get deployment token

Azure Portal → Your Static Web App → Deployment Center → GitHub Actions → Generate token

Add it as secret AZURE_STATIC_WEB_APPS_API_TOKEN in GitHub repo.

6️⃣ Commit workflow
git add .github/workflows/azure-static-web-app.yml
git commit -m "Add GitHub Actions workflow"
git push origin main

7️⃣ Verify deployment

GitHub Actions will run automatically.

Azure Static Web App will deploy build/.

Visit the URL provided by Azure to see your live app.

This README.md and guide fully document the process, both for running locally and deploying automatically.