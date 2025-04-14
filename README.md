# Postman API Tests for [Name of your API]

This repository contains two Postman Collection files for testing the Petstore and Store API, catering to different usage scenarios: manual exploration and automated testing.

## Collection Contents

### `store.collection.json` (For Manual Postman Import)

This file contains a Postman Collection designed for manual import and exploration within the Postman Desktop Application. It allows you to:

- Send individual API requests to the Store Collection.
- Examine request parameters, headers, and bodies.
- Inspect API responses, including status codes, headers, and response bodies.
- Run predefined tests within the Postman environment to validate API behavior.

To use this collection:

1.  Download the `store.collection.json` file.
2.  Open your Postman Desktop Application.
3.  Click the "Import" button.
4.  Choose "Import From File" and select the downloaded `store.collection.json` file.

### `petstore.collection.json` (For GitHub Actions Automation)

This file is specifically configured for automated testing within a GitHub Actions workflow. It contains a set of API tests focused on ensuring the reliability and correctness of the Petstore Collection in an automated continuous integration environment. These tests are designed to be run by Newman, the command-line Collection Runner for Postman.

The GitHub Actions workflow (`.github/workflows/petstore.collection.yml`) uses this collection to:

1.  Automatically run API tests on every push to the `main` branch and on manual triggers.
2.  Generate a detailed HTML report of the test results.
3.  Upload the test report as an artifact for easy access and review.

## Prerequisites

- **Postman Desktop Application:** Required for importing and exploring the `store.collection.json` manually. Download it from [https://www.postman.com/downloads/](https://www.postman.com/downloads/).
- **Newman (Command-Line Collection Runner):** Used by the GitHub Actions workflow to run the `petstore.collection.json` in an automated environment. It is installed as a project dependency in the workflow.
- **Node.js and npm:** Required for the GitHub Actions workflow to install dependencies like Newman and the HTML reporter.

## Running the `petstore.collection.json` with GitHub Actions

The automated execution of `petstore.collection.json` is managed by the GitHub Actions workflow located at `.github/workflows/postman-tests.yml`. Please refer to that file for the specific steps involved.

### Using the GitHub Actions Workflow

- **Automatic Trigger:** The workflow will automatically run whenever you push code to the `main` branch.
- **Manual Trigger:** You can also manually trigger the workflow from the "Actions" tab of your GitHub repository. Find the "Run Postman API Tests" workflow in the left sidebar and click the "Run workflow" button.
- **Viewing Results:** After the workflow run completes, you can view the logs for each step. A detailed HTML report of the test results (generated from `petstore.collection.json`) will be uploaded as an artifact named "TestReports," which you can download from the workflow run summary.
