# Sample API Deployment

## Project Overview

This project demonstrates deployment of a Node.js Express API to a VPS using PM2 for process management and GitHub Actions for CI/CD automation.

The goal was to ensure that every push to the main branch automatically deploys the latest version of the application to the VPS without manual intervention.

---

## Tech Stack

- Node.js
- Express.js
- PM2
- GitHub Actions
- Ubuntu VPS
- Git
- GitHub

---

## Project Structure

sample-api/
├── app.js
├── package.json
├── package-lock.json
├── .gitignore
└── .github/
    └── workflows/
        └── deploy.yml

---

## Local Setup

### Clone Repository

```bash
git clone <repository-url>
cd sample-api
```

### Install Dependencies

```bash
npm install
```

### Run Application

```bash
npm start
```

The API will start on:

```text
http://localhost:5010
```

---

## VPS Deployment

The application is deployed on an Ubuntu VPS provided for the assignment.

### Deployment Steps

1. SSH into VPS
2. Clone repository
3. Install dependencies
4. Start application using PM2

Example:

```bash
git clone <repository-url>
cd sample-api
npm install
pm2 start app.js --name sample-api
```

---

## PM2 Configuration

PM2 is used as a process manager because:

- Keeps application running continuously
- Automatically restarts on crashes
- Supports startup on server reboot
- Simplifies monitoring

Useful commands:

```bash
pm2 list
pm2 logs
pm2 restart sample-api
pm2 stop sample-api
```

---

## CI/CD Pipeline

GitHub Actions is configured to automatically deploy changes whenever code is pushed to the main branch.

Workflow:

1. Developer pushes code to GitHub
2. GitHub Actions triggers
3. SSH connection established to VPS
4. Latest code pulled from repository
5. Dependencies installed
6. PM2 restarts application

This eliminates the need for manual deployment.

---

## GitHub Secrets Used

Sensitive credentials are stored securely using GitHub Secrets.

Configured secrets:

- HOST
- USERNAME
- SSH_PRIVATE_KEY

No credentials are hardcoded in the workflow file.

---

## Live Endpoint

Application URL:

http://72.62.247.229:5010

---

## Architecture

Developer Machine
↓
GitHub Repository
↓
GitHub Actions
↓
Ubuntu VPS
↓
PM2
↓
Node.js Express API

---

## Assignment Objectives Completed

- VPS deployment
- PM2 process management
- GitHub Actions CI/CD
- Secure GitHub Secrets usage
- Public API endpoint

---

## Author

Soumyadeepa Dutta
