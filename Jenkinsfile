
pipeline {
    agent any 

    environment{
        PATH = "/opt/apache-maven-3.8.6/bin:$PATH"
    }

    stages {
        stage('Hello') {
            steps {
                echo "Hello"
            }
        }
        stage("Maven Build"){
            steps{
                sh "mvn clean package"
            }
        }
    }
}
