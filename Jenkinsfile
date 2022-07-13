pipeline {
    agent any

    environment {
        PATH = "/opt/apache-maven-3.8.6/bin:$PATH" 
    }
    stages {
        stage("Git Checkout") {
            steps {
                git 'https://github.com/rizwansd35/hello-world.git'
            }
        } 
        stage("Maven Build"){
            steps{
                sh "mvn clean install"
                sh "mv target/*.war target/myweb.war*"
            }
        }
        stage("Deploy"){
            steps{
                sshagent(['tomcat-new']) {
            }   ssh """
                    scp -o StirctHostKeyChecking=no target/myweb.war ec2-user@172.31.15.167:/opt/tomcate8/webapps
                    ssh ec2-user@172.31.15.167 /opt/tomcate/bin/shutdown.sh
                    ssh ec2-user@172.31.15.167 /opt/tomcate/startup.sh
                 """   

            }
        }
     }
}
