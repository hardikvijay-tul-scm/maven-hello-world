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
                     [
                         artifactId: 'code_promo',
                         classifier: '', 
                         file: 'target\MyWebApp.war', 
                         type: 'war'
                    ]
                ], 
                credentialsId: 'nexus3',
                groupId: 'in.javahome',
                nexusUrl: 'new.nexusrepocodeprom.pagekite.me',
                nexusVersion: 'nexus3',
                protocol: 'http',
                repository: 'code-promo', 
                version: '1.0.0'
            }
        }
    }
}
