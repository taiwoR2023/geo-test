pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    stages {
        stage('maven clean'){
            steps{
                sh 'mvn clean'
            }
        }
        stage ('maven install'){
            steps{
                sh 'mvn install'
            }
        }
        stage ('maven package'){
            steps{
                sh 'mvn package'
            }
        }

         stage('upload artifact'){
        steps{
            nexusArtifactUploader artifacts: [[artifactId: 'bioMedical', 
            classifier: '', file: 'target/bioMedical-0.0.2-SNAPSHOT.jar', 
            type: 'jar']], credentialsId: 'NexusID', groupId: 'qa', 
            nexusUrl: '198.58.119.40:8081/repository/rasidat/', 
            nexusVersion: 'nexus3', protocol: 'http', 
            repository: 'rasidat', version: '0.0.2'
            }
        }
    }


}