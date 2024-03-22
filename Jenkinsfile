pipeline {
    agent any

    stages {
        stage('Set Project') {
            steps {
               sh 'gcloud config set project vamsi-cloud'
            }
        }
           stage('set Account') {
            steps {
               sh 'gcloud config set account 666366464789-compute@developer.gserviceaccount.com'
            }
        }
        stage('set zone') {
            steps {
               sh 'gcloud config set compute/zone asia-east1-a'
            }
        }
        stage('create a VM') {
            steps {
               sh 'gcloud compute instances create jenkins-created-vm --network vamsi-cloud-vpc --subnet vamsi-cloud-subnet'
            }
        }

         stage('delete a VM') {
            steps {
                sh sleep 500
               sh 'gcloud compute instances delete jenkins-created-vm --quiet'
            }
        }
    }
}
