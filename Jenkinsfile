pipeline {

agent any

    stages {
        stage("Build") {

             agent {
                    label "java-gradle-slave-16"
                }

            steps {
            sh "./gradlew clean build"
            }
        }
         stage ('Build docker image') {
            agent any
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