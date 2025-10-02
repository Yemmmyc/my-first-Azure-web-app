# My First Azure Static Web App

## Overview
This project is a **React app** deployed as a **Static Web App on Azure** using **GitHub Actions**. Tailwind CSS is used for styling. The deployment ensures the app is production-ready and accessible via a public URL.

## Features
- React frontend
- Tailwind CSS styling
- Optimized production build
- Automated deployment with GitHub Actions
- Hosted on Azure Static Web Apps

## Project Structure


myapp/
├── build/ # Compiled production files
├── node_modules/ # Installed dependencies
├── public/ # Static assets
├── src/ # React source files
├── .gitignore
├── package.json # Scripts & dependencies
├── package-lock.json
├── README.md
└── myapp-build.zip # Optional: zipped build for manual upload


## Prerequisites
- Node.js (v20.x recommended)
- npm (v10.x recommended)
- Git
- GitHub account
- Azure account

## Local Development

1. Clone repository:
```bash
git clone https://github.com/Yemmmyc/my-first-Azure-web-app.git
cd my-first-Azure-web-app/myapp


Install dependencies:

npm install


Start the app locally:

npm start


Build the app for production:

npm run build


The build/ folder will contain optimized static files.

Deployment
Manual Deployment

Zip the build/ folder:

cd build
zip -r ../myapp-build.zip .


In the Azure Portal
:

Go to Static Web Apps

Choose Upload ZIP

Upload myapp-build.zip

Access your app at the URL provided by Azure.

GitHub Actions Deployment

Push your project to GitHub.

Configure Azure Static Web Apps to use GitHub Actions.

Any push to main triggers automated build and deployment.

Git Workflow

Check status:

git status


Stage changes:

git add .


Commit changes:

git commit -m "Your commit message"


Pull remote changes (if any):

git pull origin main --rebase


Push changes:

git push origin main

References

Azure Static Web Apps Documentation

React Deployment Guide

Tailwind CSS Docs