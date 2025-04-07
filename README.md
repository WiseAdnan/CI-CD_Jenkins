# CI/CD Pipeline with Jenkins for Django Notes App

This project demonstrates a hands-on CI/CD pipeline using **Jenkins**, **Docker**, **DockerHub**, and **Jenkins Shared Libraries** to automate the build and deployment of a Django Notes App.

---

## About the Project :

This pipeline performs the following tasks:

- Clones a Django Notes App from GitHub
- Builds a Docker image using the app's Dockerfile
- Pushes the image to DockerHub
- Deploys the app locally using `docker-compose`

---

##  Forked Repository Used

This pipeline is based on a **forked repository** of a Django Notes App.

- Source code: [https://github.com/WiseAdnan/django-notes-app.git](https://github.com/WiseAdnan/django-notes-app.git)

The original repository has been used only for the app source code.  
A **custom Jenkinsfile** was written from scratch and is included in this repo for the CI/CD pipeline.

---

## Jenkins Shared Library Used

This Jenkins pipeline uses a custom **shared library** containing reusable Groovy scripts for common tasks:

- `clone(branch, id, url)` – clones the GitHub repo
- `Build(imageName, tag, dockerhubUser)` – builds the Docker image
- `DockerPush(imageName, tag)` – pushes the image to DockerHub

### 🔗 Shared Library Repo

-Repo Link:  [https://github.com/WiseAdnan/Sharedlib-notesapp.git](https://github.com/WiseAdnan/Sharedlib-notesapp.git)

---

### ⚙️ Setting Up Shared Library in Jenkins

1. Go to **Manage Jenkins → Configure System**
2. Scroll to **Global Pipeline Libraries**
3. Click **Add** and configure:
   - **Name**: `shared` *(must match the Jenkinsfile: `@Library("shared")`)*  
   - **Default Version**: `main`
   - **Git Repository**: `https://github.com/WiseAdnan/Sharedlib-notesapp.git`
4. Save the configuration

---


