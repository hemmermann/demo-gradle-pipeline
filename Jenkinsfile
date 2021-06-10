pipeline {
    agent {
        label "java-gradle-slave-16"
    }

    stages {
        stage("Build") {
            steps {
            sh "gradle -v"
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