pipeline {
    agent any
    stages {
        stage('Setup') {
            steps {
                script {
			
                    sh 'az aks get-credentials --resource-group CICD --name demo'
                }
            }
        }
        stage('Build on k8') {
            steps {           
                sh 'pwd'
                sh 'cp -R helm/* .'
                sh 'ls -ltr'
                sh 'pwd'
                sh '/usr/local/bin/helm upgrade --install petclinic-app petclinic --set image.repository=democicd7.azurecr.io/cloudfreak/petclinic --set image.tag=1'
            }           
        }
    }
}

