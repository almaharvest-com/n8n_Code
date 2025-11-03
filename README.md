# ALMA's N8N Automation Platform

This repository contains the configuration, environment setup, and workflow backup for deploying n8n — the workflow automation platform — for the Alma's project.It is running inside Docker with PostgreSQL as the backend.
It includes ready-to-deploy workflows for monitoring, data backup, and AI-powered agents.

## 🧱 Architecture

Stack Components:

n8n → Workflow automation platform

PostgreSQL → Persistent database for workflows and credentials

Docker Compose → Simplified deployment and service orchestration

## 🧩 Prerequisites

## Before you start, ensure:

Docker ≥ 20.x

Docker Compose ≥ 2.x

Git installed

A server or VPS (e.g., AWS, DigitalOcean, etc.)

Access credentials for:

GitHub API

Google Drive API

Google Gemini (PaLM) API

Gmail API (OAuth)

PostgreSQL credentials

## 🐳 Docker Deployment

## Step 1: Clone the repository
git clone https://github.com/almaharvest-com/n8n_Code.git
cd n8n_Code

## Step 2: Start the containers
  docker compose up -d


## This starts:

postgres → Database container

n8n → Workflow engine

## Step 3: Verify running containers
docker ps


Expected output:

CONTAINER ID   IMAGE              STATUS          PORTS
xxxxx          n8nio/n8n:latest   Up              0.0.0.0:5678->5678/tcp
xxxxx          postgres:15        Up              5432/tcp

## Step 4: Access n8n

Open in browser:

## https://n8n.almamaps.ai/


## 📄 License & Maintainers

Maintained by: Alma Harvest Engineering Team.
