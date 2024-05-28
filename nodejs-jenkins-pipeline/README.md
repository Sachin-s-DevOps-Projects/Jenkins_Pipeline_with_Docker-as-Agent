# Node.js Jenkins Pipeline

This repository contains a sample project demonstrating a Jenkins pipeline setup for a Node.js application. The pipeline includes stages for dependency installation, testing, building, and deployment.

## Pipeline Stages

1. **Install Dependencies**
2. **Test**
3. **Build**
4. **Deploy**

## Jenkins Pipeline Configuration

Here's the Jenkins pipeline script used in this project:

```groovy
pipeline {
  agent {
    docker { image 'node:16-alpine' }
  }
  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Deploy') {
      steps {
        // Dummy deploy step, replace with your actual deployment commands
        sh 'echo "Deploying application..."'
      }
    }
  }
  post {
    always {
      deleteDir()
    }
    success {
      echo 'Pipeline succeeded!'
    }
    failure {
      echo 'Pipeline failed!'
    }
  }
}

