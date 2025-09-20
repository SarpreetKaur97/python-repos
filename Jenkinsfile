pipeline {
  agent none
  stages {
    stage('maven test') {
      agent {
        docker { image 'maven:3.8.1-adoptopenjdk-11' }
      }
      steps {
        sh 'mvn --version'
      }
    }
    stage('testingfiles') {
      agent {
        docker { image 'node:16-alpine' }
      }
      steps {
        sh 'cat tool.txt'
        sh 'sh hot.sh'
      }
    }
  }
}
