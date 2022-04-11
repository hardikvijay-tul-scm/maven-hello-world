pipeline{
    agent any

    tools {
         maven 'maven3'
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
