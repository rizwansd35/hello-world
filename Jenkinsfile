pipeline {
    agent any

    environment {
        PATH = "/opt/apache-maven-3.8.6/bin:$PATH" 
    }
    stages {
        stage("Git") {
            steps {
                git 'https://github.com/rizwansd35/hello-world.git'
            }
        } 
        stage(""){
            steps{
                sh "mvn clean install"
            }
        }
    }
