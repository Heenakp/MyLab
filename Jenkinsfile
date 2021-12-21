pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
    
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

       // Stage3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.5-SNAPSHOT.war', type: 'war']], credentialsId: '48264d93-9f5e-4ff8-b9ce-dd9318599121', groupId: 'com.vinaysdevopslab', nexusUrl: '3.134.82.119:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'VinaysDevOpsLab-SNAPSHOT', version: '0.0.5-SNAPSHOT'
      
                }
            }

      
        // Stage 4 : Deploying 
        stage ('Deploy'){
            steps {
                echo "Deploying ...."
            }
        }




    }

}
