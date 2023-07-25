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
        sh 'docker build -t cohenido/final-python:$BUILD_ID .'
      }
    }

    stage('Test') {
      steps {
        echo 'Test'
        sh 'docker run --name final-python -d -p 5000:5000 cohenido/final-python:$BUILD_ID'
        sh 'sleep 5'
        sh 'curl localhost:5000/api/doc'
        sh 'docker stop final-python && docker rm final-python'
      }
    }

    stage('Push to DockerHub') {
steps {
        withCredentials(bindings:[usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'pass', usernameVariable: 'user')]){
          echo 'Push to DockerHub'
          sh "docker login -u $user -p $pass"
          sh 'docker push cohenido/final-python:$BUILD_ID'
          }
        }
    }
    }

  }
}
