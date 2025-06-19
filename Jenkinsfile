pipeline {
    agent none

    stages {
        stage('Prepare') {
          agent any
          steps {
            checkout scm
          }
        }
        stage('Build') {
            agent {
                docker {
                    image 'node:20'
                }
            }
            steps {
                sh "npm install"
                sh "npm run build"
		archiveArtifacts artifacts: 'dist/'
            }
        }
        stage('Deploy') {
            steps {
                echo "Simulate deployment"
            }
        }
    }
}

