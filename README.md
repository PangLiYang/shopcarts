# NYU DevOps Project Template
[![Build Status](https://github.com/CSCI-GA-2820-FA24-001/shopcarts/actions/workflows/ci.yml/badge.svg)](https://github.com/CSCI-GA-2820-FA24-001/shopcarts/actions)
[![codecov](https://codecov.io/gh/CSCI-GA-2820-FA24-001/shopcarts/graph/badge.svg?token=LDC6ZRBAEN)](https://codecov.io/gh/CSCI-GA-2820-FA24-001/shopcarts)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python](https://img.shields.io/badge/Language-Python-blue.svg)](https://python.org/)

This is a skeleton you can use to start your projects

## Overview

This project template contains starter code for your class project. The `/service` folder contains your `models.py` file for your model and a `routes.py` file for your service. The `/tests` folder has test case starter code for testing the model and the service separately. All you need to do is add your functionality. You can use the [lab-flask-tdd](https://github.com/nyu-devops/lab-flask-tdd) for code examples to copy from.

## Automatic Setup

The best way to use this repo is to start your own repo using it as a git template. To do this just press the green **Use this template** button in GitHub and this will become the source for your repository.

## Manual Setup

You can also clone this repository and then copy and paste the starter code into your project repo folder on your local computer. Be careful not to copy over your own `README.md` file so be selective in what you copy.

There are 4 hidden files that you will need to copy manually if you use the Mac Finder or Windows Explorer to copy files from this folder into your repo folder.

These should be copied using a bash shell as follows:

```bash
    cp .gitignore  ../<your_repo_folder>/
    cp .flaskenv ../<your_repo_folder>/
    cp .gitattributes ../<your_repo_folder>/
```

## Contents

The project contains the following:

```text
.gitignore          - this will ignore vagrant and other metadata files
.flaskenv           - Environment variables to configure Flask
.gitattributes      - File to gix Windows CRLF issues
.devcontainers/     - Folder with support for VSCode Remote Containers
dot-env-example     - copy to .env to use environment variables
pyproject.toml      - Poetry list of Python libraries required by your code

service/                   - service python package
├── __init__.py            - package initializer
├── config.py              - configuration parameters
├── models.py              - module with business models
├── routes.py              - module with service routes
└── common                 - common code package
    ├── cli_commands.py    - Flask command to recreate all tables
    ├── error_handlers.py  - HTTP error handling code
    ├── log_handlers.py    - logging setup code
    └── status.py          - HTTP status constants

tests/                     - test cases package
├── __init__.py            - package initializer
├── factories.py           - Factory for testing with fake objects
├── test_cli_commands.py   - test suite for the CLI
├── test_models.py         - test suite for business models
└── test_routes.py         - test suite for service routes
```

## API Endpoints

Here’s a list of available API endpoints with their descriptions:

| HTTP Method | Endpoint                                      | Description                                         |
|-------------|-----------------------------------------------|-----------------------------------------------------|
| GET         | /                                             | Return some JSON about the service                  |
| GET         | /shopcarts                                    | List all shopcarts                                  |
| POST        | /shopcarts                                    | Create a new shopcart                               |
| GET         | /shopcarts/{shopcart_id}                      | Read a shopcart by its ID                           |
| PUT         | /shopcarts/{shopcart_id}                      | Update a shopcart by its ID                         |
| DELETE      | /shopcarts/{shopcart_id}                      | Delete a shopcart by its ID                         |
| GET         | /shopcarts/{shopcart_id}/items                | List all items in a shopcart                        |
| POST        | /shopcarts/{shopcart_id}/items                | Create a new item to a shopcart                     |
| GET         | /shopcarts/{shopcart_id}/items/{item_id}      | Read an item from a shopcart                        |
| PUT         | /shopcarts/{shopcart_id}/items/{item_id}      | Update an item in a shopcart                        |
| DELETE      | /shopcarts/{shopcart_id}/items/{item_id}      | Delete an item from a shopcart                      |

## ACTIONS Endpoints

| HTTP Method | Endpoint                                      | Description                                         |
|-------------|-----------------------------------------------|-----------------------------------------------------|
| PUT         | /shopcarts/{shopcart_id}/clear                                  | Clear the shopcart                  |



## Running Tests

To run the tests, use the following command:

```bash
make test
```

This will run all the test cases located in the `tests` folder, including unit tests for models and API route tests, using `pytest`. This will have a force term of at least 95% coverage.

## Running Linting

To check your code for style and linting issues, use the following command:

```bash
make lint
```

## Running Locally

To check your code server function in local, use the following command:

```bash
make run
```

This will run `honcho start`.

## Running Local K8s

To check your local cluster function well in local, use the following command:

```bash
make cluster
make build
make push
make deploy
```

## License

Copyright (c) 2016, 2024 [John Rofrano](https://www.linkedin.com/in/JohnRofrano/). All rights reserved.

Licensed under the Apache License. See [LICENSE](LICENSE)

This repository is part of the New York University (NYU) masters class: **CSCI-GA.2820-001 DevOps and Agile Methodologies** created and taught by [John Rofrano](https://cs.nyu.edu/~rofrano/), Adjunct Instructor, NYU Courant Institute, Graduate Division, Computer Science, and NYU Stern School of Business.
