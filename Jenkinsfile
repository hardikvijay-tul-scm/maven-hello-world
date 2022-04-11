pipeline{
    agent any

    tools {
         maven 'maven3'
        java 'JAVA_HOME'
    }

    stages{
        stage('clean and install'){
            steps{
                bat 'mvn clean install'
            }
        }
        stage('package'){
            steps{
               bat 'mvn package'
            }
        }
    }
}
