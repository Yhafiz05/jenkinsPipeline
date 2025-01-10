pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                sh '''
                GIT_SSH_COMMAND="ssh -o StrictHostKeyChecking=no" git clone git@github.com:Yhafiz05/jenkinsPipeline.git
                '''
            }
        }
        stage('Checkout Codebase') {
            steps {
            checkout scm: [$class: 'GitSCM',
            userRemoteConfigs: [[credentialsId: 'git',url: 'git@github.com:mnorm88/multithreading-example-1.git']]]

            }
        }
        stage('Build') {
            steps {
                sh 'gcc mt-example-0.c -lpthread'

            }
        }
        stage('Test') {
            steps {
                sh './a.out'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Done!'
            }
        }
    }
}
