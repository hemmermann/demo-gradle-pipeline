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
        agent any
         stage ('Build docker image') {
                            steps {
                                sh 'docker build -t demo-gradle-pipeline .'
                            }
                        }
                        stage ('Deploy') {
                            steps {
                                sh 'docker run -d -p 8099:8080 demo-gradle-pipeline'
                            }
                        }
    }
    post {
      always {
        cleanWs()
      }
    }
   }