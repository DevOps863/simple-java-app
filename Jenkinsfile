pipeline {
    agent {label 'slave1'}

    stages {
        stage('checkout') {
            steps {
                echo "checking out the code"
                git branch: 'main', url: 'https://github.com/DevOps863/simple-java-app.git'
            }
        }
        stage('build'){
            steps{
                echo "Building the project"
                sh 'mvn clean install'
            }
        }
        stage('Test'){
            steps{
                echo "Running test"
                sh 'mvn test'
            }
        }
        stage ('Deploy'){
            steps{
                echo " Deploying the application"
                sh "cp target/simple-java-app-1.0-SNAPSHOT.jar /home/ec2-user/opt/deployments/simple-java-app.jar" 
                
            }
        }
        
    }
}
