# CloudX CI/CD Network Validation

## Overview
This repository contains the materials needed to recreate my CloudX 2024 presentation on implementing network validation using CI/CD pipelines. The project showcases how to automate network validation processes using modern DevOps practices.

## Getting Started

### 1. Fork and Clone
```bash
# Fork this repository using GitHub UI
git clone https://github.com/[YOUR_USERNAME]/cloudx_cicd_network_validation.git
cd cloudx_cicd_network_validation
```

### 2. Arista cEOS Image Setup
Due to licensing requirements, the Arista cEOS image must be downloaded separately:

1. Download the cEOS image from [Arista's Software Download Page](https://www.arista.com/en/support/software-download)
2. Configure Git LFS in your repository:
   ```bash
   git lfs install
   git lfs track "*.tar"
   git add .gitattributes
   ```
3. Add the cEOS image to your repository:
   ```bash
   git add [cEOS image file]
   git commit -m "Add cEOS image"
   git push origin [branch]
   ```

### 3. CI/CD Pipeline
When you create a Pull Request, GitHub Actions will:
1. Download the cEOS image from Git LFS
2. Run pre-validation on device configs
3. Set up the test environment using containerlab
4. Run post-validation

## Usage
1. Make your network configuration changes
2. Create a new branch:
   ```bash
   git checkout -b feature/your-change
   ```
3. Commit your changes and push:
   ```bash
   git add .
   git commit -m "Description of your changes"
   git push origin feature/your-change
   ```
4. Create a Pull Request on GitHub
5. Monitor the automated tests in the GitHub Actions tab


## Note
you can use github codespaces to create containerlab network to play around and manipulate the configs