pipeline {
  agent {label 'Jenkins-agent'}
  tools {
  maven 'Maven3'
  jdk 'Java17'
}
  stages{
    stage("Cleanup workspace"){
      steps{
        cleanWs()
      }
    }
   stage("checkout from git"){
     steps{
       git branch: 'main', credentialsId: 'github', url: 'https://github.com/santhosh-devops-aws/register-app'
     }
   } 
  stage("Build application"){
    steps{
          sh "mvn clean package"
    }
  }
stage("Test application"){
    steps{
          sh "mvn test"
    }
  }
  }
}
