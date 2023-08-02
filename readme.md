# Symfony 6 Web Scraper

This is a Symfony application that has been containerized with Docker. Its primary function is to perform web scraping by retrieving data from https://rekvizitai.vz.lt/en/company-search/ based on a registration code. The scraper extracts essential information from the company profile, such as the Company name, Registration code, VAT, Address, and Mobile phone. Moreover, it also scrapes details about the company's turnover.

## Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)


## Requirements

Before getting started, ensure that your system meets the following requirements:

- Docker 19.03.0+
- ensure that following ports are not in use: `80` `443` `5672` `15672` `6379`. If already in use, configure it from docker/docker-compose.yml` file.

## Installation

Follow the step below to set up the Application:

1. Clone the repository:

```bash
git clone git@github.com:mofaruk/symfony-scraper.git
```

## Configuration
1. Configure docker
- clone  a `.env` file from `docker/mysql/.env.example` on `docker/mysql` directory and configure the variables
- clone  a `.env` file from `docker/rabbitmq/.env.example` on `docker/rabbitmq` directory and configure the variables
- clone  a `.env` file from `docker/redis/.env.example` on `docker/redis` directory and configure the variables  
  
additionally you can configure custom configuration for php using `docker/php/custom.ini` file.

2. Configure application.
Before running the application, you may need to configure some settings. Key configuration files are located in the `config/` directory. These files include:

- `config/packages/framework.yaml`: General framework configuration.
- `config/packages/doctrine.yaml`: Doctrine ORM configuration.
- `config/packages/security.yaml`: Security settings and access control.
- `config/packages/twig.yaml`: Twig templating engine configuration.
- `config/routes.yaml`: Application routes.
  
Additionally, you may need to configure the database connection and other environment-specific settings in `.env` or `.env.<env:local|prod|test>` files.

## Usage

To run the application, use the following commands:

1. Navigate to the docker directory of the project:

```bash
cd symfony-scraper/docker
```

2. Initialize docker containers:

```bash
docker compose up -d
```

This will start a local development server, and you can access the application in your browser at `http://localhost`.



