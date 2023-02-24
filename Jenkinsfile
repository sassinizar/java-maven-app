pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('jenkins-credentials')
    }
    stages {
        stage("init") {
            steps {
                echo 'initialisation stage version = ${NEW_VERSION}'
            }
        }
        stage("build jar") {
            steps {
              echo 'initialisation stage'
            }
        }
        stage("build image") {
            steps {
               
                    echo 'building image'
            }
        }
        stage("deploy") {
            steps {
                  echo 'deploying stage .......'
                echo 'deploying with jenkins server credentials ${SERVER_CREDENTIALS}'
                sh "${SERVER_CREDENTIALS}"
            }
        }
    }   
}
