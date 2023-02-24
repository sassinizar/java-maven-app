pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
       
        stage("build jar") {
            steps {
                script {
                    echo 'building the application...'
                    sh 'mvn package'
                }
            }
        }
        stage("build docker image") {
            steps {
                script {
                    echo 'building the docker image...'
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'docker', usernameVariable: 'docker')]){
                            sh 'docker build -t nizarsassi/demo-app:jma-2.0'
                            sh "echo $docker | docker login -u $docker --password-stdin"
                            sh 'docker push nizarsassi/demo-app:jma-2.0 '
                    }
                    
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    echo 'deploying image...'
                }     
            }
        } 
      }
