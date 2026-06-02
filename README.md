# Sample API Deployment

## Overview

Node.js Express API deployed on a VPS with PM2 and GitHub Actions CI/CD.

## Tech Stack

- Node.js
- Express
- PM2
- GitHub Actions
- Ubuntu VPS

## Local Setup

```bash
npm install
npm start
```

## Live Endpoint

http://72.62.247.229:5010

## CI/CD Flow

Push to main branch → GitHub Actions → SSH to VPS → Pull latest code → npm install → PM2 restart

## PM2 Process

sample-api
