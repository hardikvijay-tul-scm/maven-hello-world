pipeline{
    agent any

    tools {
         maven 'maven3'
        jdk 'JAVA_HOME'
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
        stage('Upload War to Nexus') {
            steps {
                    nexusArtifactUploader artifacts: [
                        [artifactId: 'code_promo', 
                         classifier: '', 
                         file: '..\\target\\MyWebApp.war', type: 'war']
                        ],
                        credentialsId: 'nexus3', 
                        groupId: 'code_promo', 
                        nexusUrl: 'localhost:8081', 
                        nexusVersion: 'nexus3', 
                        protocol: 'http', 
                        repository: 'code_promo', 
                        version: '1.0.0'
            }
        }
    }
}
