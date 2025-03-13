OpenShift Code Coverage Report Generator
Overview
This repository contains a Go-based CLI tool designed to fetch and report test coverage data for all repositories under the OpenShift organization. The tool integrates with GitHub API and Codecov API to provide insights into test coverage across various repositories.

It provides:

A summary of test coverage percentages for all OpenShift repositories.
The ability to generate detailed per-file coverage reports (if the -v flag is enabled).
Machine-readable CSV output for further analysis.
____________
Prerequisites
*Install Go (if not installed)
Ensure Go is installed on your machine. You can download it from Go's official website.

To check if Go is installed:

bash
Copy
Edit
go version
*Set Up API Tokens
The script requires authentication tokens for both GitHub API and Codecov API. These must be set as environment variables.

Set API Tokens:
bash
Copy
Edit
export GITHUB_TOKEN="your_github_token"
export CODECOV_TOKEN="your_codecov_token"
Replace your_github_token and your_codecov_token with actual values.
_____________
