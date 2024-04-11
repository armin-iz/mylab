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

// publish the artifacts to Nexus

stage ('publish to nexus'){
    steps{
        nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4.war', type: 'war']], credentialsId: 'bd392eda-795c-462c-88ce-355b8dc3d532', groupId: 'com.vinaysdevopslab', nexusUrl: '192.168.1.40:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'ArminsDevopsLab-RELEASE', version: '0.0.4'
    }
}

    // Stage3 : Deploying
    stage ('deploy'){
        steps{
            echo 'deploying......'
        }
    }
        // Stage3 : Publish the source code to Sonarqube
        // stage ('Sonarqube Analysis'){
        //     steps {
        //         echo ' Source code published to Sonarqube for SCA......'
        //         withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
        //              sh 'mvn sonar:sonar'
        //         }

        //     }
        // }

        
        
    }

}