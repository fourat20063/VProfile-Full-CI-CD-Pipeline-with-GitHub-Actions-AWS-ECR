# VProfile-Full-CI-CD-Pipeline-with-GitHub-Actions-AWS-ECR

This workflow implements a complete CI/CD pipeline for the VProfile application, automating build, testing, security scanning, and Docker image deployment to Amazon ECR.
It is triggered on every push or pull request to the main branch, manual dispatch, and a scheduled daily run.

Pipeline Stages

1. 🔨 Build Stage

Checks out the repository

Builds the application using Maven

Generates a .war artifact

Uploads artifacts for later stages

Notifies on failures

2. 🧪 Testing Stage

Runs unit tests and Checkstyle on main

Skips tests on other branches

3. 🔐 Security Scan

Uses Trivy to scan the filesystem for vulnerabilities

Uploads scan results as an artifact

4. 🚀 Build & Publish Docker Image

Runs only on main after all previous jobs succeed

Authenticates to AWS using GitHub Secrets

Builds a Docker image using your multistage Dockerfile

Pushes the image to AWS ECR

Tags image with the Git commit SHA

This pipeline ensures code quality, security compliance, and automated delivery to your container registry.
