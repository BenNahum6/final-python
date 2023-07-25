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
        git(url: 'https://github.com/Ido-Cohen/final-python.git', branch: 'main', changelog: true, poll: true)
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