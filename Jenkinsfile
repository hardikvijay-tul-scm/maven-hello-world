pipeline{
    agent any

    tools {
         maven 'maven3'
        java 'jdk'
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
