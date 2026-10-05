# Movie Picture Pipeline — Project Evidence

## Project Overview

This project implements a CI/CD pipeline for the Movie Picture application using GitHub Actions, Docker, Amazon ECR, Amazon EKS, Kubernetes, and Kustomize.

The implementation covers both the frontend and backend applications. The CI workflows validate changes through linting, testing, and Docker image builds, while the CD workflows build and publish images and deploy the applications to AWS EKS.

The project repository is:

`Murali-77/Murali-77-Movie-Picture-Pipeline-Udacity`

## GitHub Actions Workflows

The workflow definitions are stored under:

`.github/workflows/`

The project contains these four workflows:

- `frontend-ci.yaml`
- `backend-ci.yaml`
- `frontend-cd.yaml`
- `backend-cd.yaml`

The frontend and backend CI workflows run for pull requests and perform the required validation steps.

The frontend CI workflow handles dependency installation, linting, testing, and the frontend build.

The backend CI workflow installs the Python development dependencies, runs linting and tests, and builds the backend Docker image.

The CI workflows were also verified through a pull request before the changes were merged into `main`.

Evidence:

- `pull_request_ci_checks.jpg`
- `github_action_workflows.jpg`
- `github_action_success.jpg`

## Deployment Flow

The deployment implementation uses Docker, Amazon ECR, Amazon EKS, Kubernetes, and Kustomize.

For the frontend and backend deployment workflows, the process includes:

1. Authenticating with AWS.
2. Logging Docker into Amazon ECR.
3. Building the application Docker image.
4. Pushing the image to ECR.
5. Configuring access to the EKS cluster.
6. Applying the Kubernetes/Kustomize configuration.

The Kubernetes deployment and service configuration is maintained inside the respective application `k8s` directories.

## Frontend Verification

During the project execution, I verified the frontend application through its AWS Elastic Load Balancer endpoint.

The application displayed the Movie List and Movie Details pages, including movies such as:

- Top Gun: Maverick
- Sonic the Hedgehog
- A Quiet Place

The frontend verification screenshots are:

- `frontend_verification_01.jpg`
- `frontend_verification_02.jpg`
- `frontend_verification_03.jpg`
- `frontend_verification_04.jpg`

The frontend endpoint used during the verification period was:

`http://a5c62f3bdf1d84b13af13d1044f39d8b-384117127.us-east-1.elb.amazonaws.com`

This endpoint is currently inactive. It identifies the endpoint that was used to verify the deployment during the project execution.

## Backend Verification

The backend application was also verified through its `/movies` API endpoint.

The endpoint used during the verification period was:

`http://aeb93f782c26d45cebca64194f9158af-2081483282.us-east-1.elb.amazonaws.com/movies`

The API returned the expected movie data during verification.

Evidence:

- `backend_movies_api.jpg`

The backend endpoint is currently inactive and is included to document the endpoint used during project verification.

## AWS and Kubernetes Status

The frontend and backend applications were successfully deployed and tested on AWS EKS during the project execution.

At the time of final submission, the previously generated ELB endpoints are no longer active because the EKS worker-node environment is currently unavailable.

Therefore, the final submission does not claim that the ELB URLs are currently reachable. The screenshots document the frontend, backend API, and GitHub Actions verification performed while the deployment environment was available.

## Final Repository Contents

The final repository contains the application source code, GitHub Actions workflows, Kubernetes/Kustomize configuration, Terraform configuration, and project evidence.

The repository used for the final submission is:

`Murali-77/Murali-77-Movie-Picture-Pipeline-Udacity`

The screenshots included with the project provide supporting evidence of the CI/CD workflow execution and application verification.
