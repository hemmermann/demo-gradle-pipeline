pipeline {
    agent {
        label "java-gradle-slave-16"
    }

    stages {
        stage("Build") {
            steps {
            sh "./gradlew clean build"
            }
        }
    }

    post {
      always {
        cleanWs()
      }
    }
   }