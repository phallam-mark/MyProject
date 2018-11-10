pipeline {
  agent { label 'master' }
  tools {
	maven 'Maven3'
  }  
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/phallam-mark/MyProject.git'
      }
    }
    stage('build'){
      steps{
        sh 'mvn clean compile'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      } 
    }
    stage('Package'){
      steps{
        sh 'mvn package'
      }
    }
  }
 }
