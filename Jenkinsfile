pipeline {

 agent any

 environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
 }

 stages {

  stage('Clone Repository') {
   steps {
    git branch : 'main',
        url: 'https://github.com/Ash-the-k/ci-cd-web-app.git'
   }
  }

  stage('Build Docker Image') {
   steps {
    bat 'docker build -t web-devops-app .'
   }
  }

  stage('Run Docker Container') {
   steps {
    bat 'docker run -d -p 8080:80 --name web-container web-devops-app'
   }
  }

 }

}