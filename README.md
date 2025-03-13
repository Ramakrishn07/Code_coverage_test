### OpenShift Code Coverage Report Generator
***Overview***
This repository contains a Go-based CLI tool designed to fetch and report test coverage data for all repositories under the OpenShift organization. The tool integrates with GitHub API and Codecov API to provide insights into test coverage across various repositories.

**Features**

A summary of test coverage percentages for all OpenShift repositories.
The ability to generate detailed per-file coverage reports (if the -v flag is enabled).
Machine-readable CSV output for further analysis.
____________
**Prerequisites**
**Set Up API Tokens**
The script requires authentication tokens for both GitHub API and Codecov API. These must be set as environment variables.

Set API Tokens:
(```export GITHUB_TOKEN="your_github_token"
   export CODECOV_TOKEN="your_codecov_token"```) 
Replace your_github_token and your_codecov_token with actual values.
_____________
**Installation**
Clone the repository
Install dependencies (go mod tidy)
_____________
**Usage**
Run the script (Basic Usage) 
(```go run main.go```)
This fetches test coverage data for all OpenShift repositories and displays a summary.

**Run with verbose mode (-v)**
(```go run main.go -v```)
The -v flag provides a detailed per-file test coverage report and generates a CSV report for each repository.
______________
**How It Works**
*Fetching OpenShift Repositories
The script uses GitHub API to list all repositories under OpenShift.
It fetches repositories in batches using pagination.*

*Fetching Code Coverage Data
It queries Codecov API for each repository.
It retrieves the latest test coverage percentage.
Determines whether a repository is configured in Codecov.*

*Displaying Coverage Data
Outputs repositories sorted by coverage percentage (ascending order).
Marks repositories with no coverage data as "Not Configured".*

*Generating CSV Reports (if -v is used)
If the verbose mode is enabled:
A detailed per-file coverage breakdown is fetched.
The report includes:
File name
Total lines
Covered lines
Missed lines
Coverage percentage
Reports are stored as (```detailed_<repo_name>_coverage_report.csv```)


**Example Output**
*Summary Output*
(```Repository, Coverage Percentage
repo-a, 85.30%
repo-b, 78.40%
repo-c, Not Configured```)

*Verbose Mode Output*
(```Detailed coverage report generated for repo-a: detailed_repo-a_coverage_report.csv
Detailed coverage report generated for repo-b: detailed_repo-b_coverage_report.csv```)



