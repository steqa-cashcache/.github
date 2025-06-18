[ru](https://github.com/steqa-cashcache/react-app) [en](https://github.com/steqa-cashcache/.github/blob/main/locale/react-app/README.en.md)

# CashCache :coin: React App
:warning: This repository is part of the [CashCache](https://github.com/steqa-cashcache) project :warning:  
For installation and startup information, see the [README](https://github.com/steqa-cashcache/.github/blob/main/locale/README.en.md)


![GitHub Release](https://img.shields.io/github/v/release/steqa-cashcache/react-app)
![License](https://img.shields.io/badge/license-MIT-green)


![TypeScript](https://img.shields.io/badge/TypeScript-017acc?style=flat&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-49aabf?style=flat&logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-671ddf?style=flat&logo=axios&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat&logo=react-router&logoColor=white)

## Содержание
1. [Description](#description)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Interface Demo](#interface-demo)
5. [License](#license)


## Description
Web interface for the CashCache personal finance management system.  
Allows managing accounts, transactions, templates, and configuring regular transactions via a user-friendly UI.


## Features
- JSON Web Token stored in `localStorage`
- After login, the token is used in Authorization headers for all requests 
- Integration with the [backend API](https://github.com/steqa-cashcache/api) via REST
- Interactive forms for CRUD operations
- Uses modern stack: React, TypeScript, Vite
- Responsive design for mobile and desktop


## Project Structure
```
src
├── api                # API layer: requests, data schemas, axios config
│   ├── requests       # Specific requests by entities (account, auth, category, transaction, etc.)
│   └── schemas        # Types and data schemas for API
├── blocks             # Blocks — large UI components with logic and styles
├── components         # Small reusable UI components
├── contexts           # React context for authorization
├── hooks              # Custom React hooks (useHttpRequest, useValidator, etc.)
├── locale             # Localization (e.g. Russian locale for errors)
├── pages              # App pages
├── routers            # React Router configuration
├── utils              # Helper functions (date, money handling, etc.)
└── validators         # Validation functions (email, date, password, etc.)

```


## Interface Demo
### Screenshots
![Примеры интерфейса](https://github.com/steqa-cashcache/.github/blob/main/media/interface.png?raw=true)

### Login
![Вход](https://github.com/steqa-cashcache/.github/blob/main/media/login.gif?raw=true)

### Add, Edit, Delete Income
![Добавление, изменение, удаление дохода](https://github.com/steqa-cashcache/.github/blob/main/media/income.gif?raw=true)

### Add, Edit, Delete Expense
![Добавление, изменение, удаление расхода](https://github.com/steqa-cashcache/.github/blob/main/media/expense.gif?raw=true)

### Add, Edit, Delete Transfer
![Добавление, изменение, удаление расхода](https://github.com/steqa-cashcache/.github/blob/main/media/transfer.gif?raw=true)

### Accounts Page
![Страница аккаунтов](https://github.com/steqa-cashcache/.github/blob/main/media/account.gif?raw=true)

### Add, Edit, Delete Account
![Добавление, изменение, удаление аккаунта](https://github.com/steqa-cashcache/.github/blob/main/media/account.gif?raw=true)

### Add, Edit, Delete Category
![Добавление, изменение, удаление категории](https://github.com/steqa-cashcache/.github/blob/main/media/category-settings.gif?raw=true)

### Add, Edit, Delete Transaction Template
![Добавление, изменение, удаление шаблона транзакции](https://github.com/steqa-cashcache/.github/blob/main/media/transaction-template-settings.gif?raw=true)

### Add, Edit, Delete Regular Transaction
![Добавление, изменение, удаление регулярной транзакции](https://github.com/steqa-cashcache/.github/blob/main/media/transaction-template-settings.gif?raw=true)


## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/steqa-cashcache/react-app?tab=MIT-1-ov-file) file for more details.
