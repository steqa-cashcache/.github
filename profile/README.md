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


## Содержание
1. [Описание](#описание)
2. [Возможности](#возможности)
3. [Репозитории](#репозитории)
4. [Требования](#требования)
5. [Установка](#установка)
6. [Использование](#использование)
7. [Интерфейс](#интерфейс)


## Описание
Веб-приложение для удобного управления личными финансами через Telegram WebApp и веб-браузер.


## Возможности
- **Множественные аккаунты** — веди отдельные бюджеты для "Наличных", "Валютных", "Банковских" и других счетов.
- **Учет доходов и расходов с категориями** — систематизируй финансы по понятным группам.
- **Переводы между счетами** — легко перемещай деньги внутри своих аккаунтов.
- **Регулярные транзакции** — настрой повторяющиеся поступления и траты для автоматического учёта.
- **Шаблоны транзакций** — создай шаблон расхода или дохода, чтобы быстро добавлять однотипные операции.
- **Веб-клиент, интегрированный с Telegram WebApp** — пользуйся приложением прямо внутри Telegram.


## Репозитории
### [`api`](https://github.com/steqa-cashcache/api)
> Основной REST API. Java + Spring Boot, PostgreSQL, gRPC.
### [`repetition-service`](https://github.com/steqa-cashcache/repetition-service)
> Микросервис для регулярных транзакций. Java + Spring Boot, MongoDB, RabbitMQ, gRPC.
### [`react-app`](https://github.com/steqa-cashcache/react-app)
> Веб-клиент на React + TypeScript.


## Требования
Убедитесь, что Docker установлен и запущен на вашей системе. Скачать Docker можно [здесь](https://www.docker.com/get-started).  
Затем вам понадобится Node.js и npm.  

**Ubuntu/Debian**
  ```bash
  curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
  sudo apt install -y nodejs
  ```
**Arch**
  ```bash
  sudo pacman -S nodejs npm
  ```


## Установка

Создайте каталог проекта:
    
  ```bash
  mkdir budget-manager
  cd budget-manager
  ```

### Запуск API
1. Клонируйте репозиторий:

    ```bash
    git clone https://github.com/steqa-cashcache/api
    ```
2. Переименуйте `.env.example` в `.env` и обновите его согласно вашим настройкам.

3. Соберите и запустите Docker-контейнеры:

    ```bash
    cd api
    docker compose up --build
    ```


### Запуск сервиса регулярных транзакций
1. Клонируйте репозиторий:

    ```bash
    git clone https://github.com/steqa-cashcache/repetition-service
    ```
2. Переименуйте `.env.example` в `.env` и обновите его согласно вашим настройкам.

3. Соберите и запустите Docker-контейнеры:

    ```bash
    cd repetition-service
    docker compose up --build
    ```

### Запуск веб-клиента
1. Клонируйте репозиторий:

    ```bash
    git clone https://github.com/steqa-cashcache/react-app
    ```
2. Установите зависимости:

   ```bash
    npm install
    ```
3. Запустите клиент:

    ```bash
    cd react-app
    npm run dev
    ```


## Использование
- API доступен по: http://localhost:5252
- Swagger UI: http://localhost:5252/api/v1/swagger-ui
- Веб-клиент: http://localhost:5173


## Интерфейс
![Примеры интерфейса](https://github.com/steqa-cashcache/.github/blob/main/media/interface.png?raw=true)

