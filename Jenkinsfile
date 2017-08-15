#!/usr/bin/env groovy

def buildmessage = "Building .. ${env.BUILD_ID}"
pipeline {
    agent any
    //setting environment variable, to be availeble through jenkins file
        environment {
            buildmessage_env = "setting environment"
        }

    stages {
        
        stage('Build') {
            environment {
                l_env_var = "setting local environment variable for build stage only"
            }
            steps {
                echo "${env.buildmessage_env}"
                echo "${buildmessage}"
                echo "${env.l_env_var}"
                echo "archiving artifacts, archiveArtifacts artifacts: '**' "
            }
        }
        stage('Test') {
            steps {
                echo "Testing ..  and avoid failingby using inline shell conditional || true "
                echo "collect junit test results using junit step"
            }
        }
        stage('Deploy') {
            when {
                expression{
                    currentBuild.result == null || currentBuild.result == 'SUCCESS'
                }
            }
            steps {
                echo "Checked the result of previous stages, "
                echo "Deploying .. "
            }
        }
    }
}
//checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '5160b6a2-90d4-4d1e-b5b4-21e85c7f6c95', url: 'https://github.com/faizan80/jenkins-pipeline.git']]])
