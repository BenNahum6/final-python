pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Checkout code') {
      steps {
        echo 'Checkout code'
      }
    }

    stage('Build') {
      steps {
        echo 'Build'
      }
    }

    stage('Test') {
      steps {
        echo 'Test'
      }
    }

    stage('Push to DockerHub') {
      steps {
        echo 'Push to DockerHub'
      }
    }

  }
}