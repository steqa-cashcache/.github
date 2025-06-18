[ru](https://github.com/steqa-cashcache/repetition-service) [en](https://github.com/steqa-cashcache/.github/blob/main/locale/repetition-service/README.en.md)

# CashCache :coin: Repetition Service
:warning: This repository is part of the [CashCache](https://github.com/steqa-cashcache) project :warning:  
For installation and startup information, see the [README](https://github.com/steqa-cashcache/.github/blob/main/locale/README.en.md)


![GitHub Release](https://img.shields.io/github/v/release/steqa-cashcache/repetition-service)
![License](https://img.shields.io/badge/license-MIT-green)


![Java](https://img.shields.io/badge/Java-f58312.svg?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6db240?style=flat&logo=springboot&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-00694a.svg?style=flat&logo=mongodb&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6404.svg?style=flat&logo=rabbitmq&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ed?logo=docker&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-2ca6af.svg?style=flat&logo=grpc&logoColor=white)


## Table of Contents
1. [Description](#description)
2. [Features](#features)
3. [gRPC Interaction](#grpc-interaction)
4. [Data Storage Schema](#data-storage-schema)
5. [License](#license)


## Description
A microservice for managing regular transactions.  
Repetition rules are stored in MongoDB, and tasks are scheduled and managed via RabbitMQ.  
Once a task is executed, a gRPC request is sent to the [api](https://github.com/steqa-cashcache/api) service to create a transaction.


## Features
- Manage regular transaction rules (create, delete)
- Supports multiple repetition modes:
  - `FIXED_MONTH` — repeat every month on a specific day
  - `FIXED_YEAR` — repeat every year on a specific day and month
  - `INTERVAL_DAY` — repeat every N days
  - `INTERVAL_SECONDS` — repeat every N seconds
- Creates tasks for RabbitMQ to be executed on schedule
- Calls gRPC methods of the [api](https://github.com/steqa-cashcache/api) service to create transactions based on rules


## gRPC Interaction

The repetition-service provides a `RepetitionService` gRPC service, which is used by the REST API to add and remove regular rules.

The [api](https://github.com/steqa-cashcache/api) service calls `AddRule` and `DeleteRule` methods to manage regular rules.

Upon task execution, the service reads the rule from MongoDB, updates the `nextExecution` field according to the parameters, creates a new task in RabbitMQ, and sends a gRPC request to the [api](https://github.com/steqa-cashcache/api) to create a transaction.


## Data Storage Schema
Repetition rules are stored in MongoDB in a collection, for example:

```json
{
  "_id": {"$oid": "6852e79aede3047b341e706a"},
  "_class": "ru.steqa.repetitionservice.scheme.rabbit.repetition.IntervalSecondRepetition",
  "deleted": false,
  "mode": "INTERVAL_SECOND",
  "nextExecution": {"$date": "2025-06-18T16:22:45.000Z"},
  "seconds": 60,
  "transactionId": 1,
  "transactionType": "DEFAULT",
  "userId": 1
}
```

Rules have different parameters depending on the `mode`:
- For `FIXED_MONTH` — only `day` is stored.
- For `FIXED_YEAR` — `day` and `month` are stored.
- For `INTERVAL_DAY` — number of days (`days`).
- For `INTERVAL_SECOND` — number of seconds (`seconds`).


## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/steqa-cashcache/repetition-service?tab=MIT-1-ov-file) file for more details.
