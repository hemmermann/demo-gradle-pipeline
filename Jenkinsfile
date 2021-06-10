pipeline {
    agent {
        label "java-gradle-slave-16"
    }

    stages {
        stage("Build") {
            steps {
            sh "sleep 1m"
            sh "gradle --version"
            sh "gradle clean build"
            }
        }
    }

    post {
      always {
        cleanWs()
      }
    }
   }