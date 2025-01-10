pipeline{
  agent any 
  stages {

    stage('Checkout'){
      steps{
        checkout scm : [$class: 'GitSCM', userRemoteConfigs:[[credentialsId : 'github-key', url : 'git@github.com:moss-n/multithreading-example-1.git']]]
      }
    }
    stage('Build'){
      steps{
        sh 'gcc mt-example-0.c -lpthread'
    }
    stage('Test'){
      steps{
        sh './a.out'
      }
    }
  }
}
