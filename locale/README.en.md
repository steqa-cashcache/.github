[ru](https://github.com/steqa-cashcache) [en](https://github.com/steqa-cashcache/.github/blob/main/locale/README.en.md)

# CashCache :coin:

![Java](https://img.shields.io/badge/Java-f58312.svg?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6db240?style=flat&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-326790.svg?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-00694a.svg?style=flat&logo=mongodb&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6404.svg?style=flat&logo=rabbitmq&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-017acc?style=flat&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-49aabf?style=flat&logo=react&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ed?logo=docker&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-2ca6af.svg?style=flat&logo=grpc&logoColor=white)

## Table of Contents
1. [Description](#description)  
2. [Features](#features)  
3. [Repositories](#repositories)  
4. [Requirements](#requirements)  
5. [Setup](#setup)  
6. [Usage](#usage)  
7. [Interface](#interface)  

## Description
A web application for convenient personal finance management via Telegram WebApp and web browser.

## Features
- **Multiple accounts** — manage separate budgets for "Cash", "Foreign Currency", "Bank Accounts", and more.  
- **Income and expense tracking with categories** — organize your finances into clear, structured groups.  
- **Transfers between accounts** — easily move money between your own accounts.  
- **Recurring transactions** — set up automatic recurring income or expenses.  
- **Transaction templates** — create reusable income or expense templates for faster input.  
- **Web client integrated with Telegram WebApp** — use the app directly inside Telegram.  

## Repositories
### [`api`](https://github.com/steqa-cashcache/api)
> Main REST API. Java + Spring Boot, PostgreSQL, gRPC.

### [`repetition-service`](https://github.com/steqa-cashcache/repetition-service)
> Microservice for recurring transactions. Java + Spring Boot, MongoDB, RabbitMQ, gRPC.

### [`react-app`](https://github.com/steqa-cashcache/react-app)
> Web client built with React + TypeScript.

## Requirements
Make sure Docker is installed and running on your system. You can download Docker [here](https://www.docker.com/get-started).  
You’ll also need Node.js and npm.

**Ubuntu/Debian**
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install -y nodejs
```

**Arch**
```bash
sudo pacman -S nodejs npm
```

## Setup

Create the project directory:
```bash
mkdir budget-manager
cd budget-manager
```

### Launching the API
1. Clone the repository:
    ```bash
    git clone https://github.com/steqa-cashcache/api
    ```

2. Rename `.env.example` to `.env` and configure it.

3. Build and run Docker containers:
    ```bash
    cd api
    docker compose up --build
    ```

### Launching the Repetition Service
1. Clone the repository:
    ```bash
    git clone https://github.com/steqa-cashcache/repetition-service
    ```

2. Rename `.env.example` to `.env` and configure it.

3. Build and run Docker containers:
    ```bash
    cd repetition-service
    docker compose up --build
    ```

### Launching the Web Client
1. Clone the repository:
    ```bash
    git clone https://github.com/steqa-cashcache/react-app
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start the client:
    ```bash
    cd react-app
    npm run dev
    ```

## Usage
- API available at: http://localhost:5252  
- Swagger UI: http://localhost:5252/api/v1/swagger-ui  
- Web client: http://localhost:5173  

## Interface
![Interface Examples](https://github.com/steqa-cashcache/.github/blob/main/media/interface.png?raw=true)
