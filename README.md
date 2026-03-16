# GitHub Actions Deployment Workflow 🚀

project url: https://roadmap.sh/projects/github-actions-deployment-workflow

This repository is a simple project designed to help you learn the fundamentals of **Continuous Integration (CI)** and **Continuous Deployment (CD)** using **GitHub Actions**.

The repository contains a simple `index.html` file that is automatically deployed to **GitHub Pages** whenever changes are pushed to the `main` branch.

---

## 🛠 Prerequisites: GitHub Settings

Before the deployment workflow can work, you need to configure your GitHub repository settings:

### 1. Enable GitHub Actions
1. Go to your repository on GitHub.
2. Click on the **Settings** tab.
3. In the left sidebar, under "Code and automation," click **Actions** -> **General**.
4. Under "Actions permissions," ensure **Allow all actions and reusable workflows** (or at least "Allow select actions") is selected.
5. Scroll down to "Workflow permissions" and ensure **Read and write permissions** is selected.

### 2. Configure GitHub Pages Source
1. In the **Settings** tab, click **Pages** in the left sidebar.
2. Under **Build and deployment** -> **Source**, select **GitHub Actions** from the dropdown menu.
   - *Note: Do not select "Deploy from a branch" if you want to use the included workflow.*

---

## 🔄 How the CI/CD Workflow Works

The automation is defined in the [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) file. Here's a breakdown of what happens:

1.  **Trigger**: The workflow starts automatically when:
    - Code is pushed to the `main` branch.
    - The `index.html` file is modified.
    - You manually trigger it via the "Run workflow" button in the **Actions** tab.
2.  **Environment**: It runs on a virtual machine using the latest version of Ubuntu (`ubuntu-latest`).
3.  **Steps**:
    - **Checkout**: It pulls the latest code from your repository.
    - **Upload Artifact**: It packages the repository contents (the `index.html`) as an artifact for GitHub Pages.
    - **Deploy**: It takes that artifact and publishes it to your GitHub Pages site.

---

## 🚀 Getting Started

1.  **Fork** this repository.
2.  Follow the **Settings** steps mentioned above.
3.  Make a small change to `index.html` (e.g., change the "Hello" message).
4.  **Push** your changes to the `main` branch.
5.  Go to the **Actions** tab to watch your deployment in real-time!

