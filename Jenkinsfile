#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building .. "
            }
        }
        stage('Test') {
            steps {
                echo "Testing .. "
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying .. "
            }
        }
    }
}
//checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '5160b6a2-90d4-4d1e-b5b4-21e85c7f6c95', url: 'https://github.com/faizan80/jenkins-pipeline.git']]])