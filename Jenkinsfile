pipeline {
  agent any
  stages {
    stage('code checkout') {
      steps {
        git(url: 'https://github.com/TrippleA-Ashaba/CI_CD.git', branch: '_albert')
      }
    }

    stage('log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('build image') {
      steps {
        sh 'docker build -f Dockerfile .'
      }
    }

    stage('log into Dockerhub') {
      environment {
        DOCKERHUB_USER = 'trippleaunit'
        DOCKERHUB_PASSWORD = 'Safari170692'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}