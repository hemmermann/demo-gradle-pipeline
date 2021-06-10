pipeline {
    agent {
        label "java-slave-14"
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