pipeline{
  agent{
    label 'slave1'
  }

  stages{
    stage('Checkout'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: "https://github.com/Vijay-kumar-N/maven_jan_24.git", credentialsId: 'git_token']]])
      }
    }
    
    stage('Clean'){
      steps{
        sh '''
          cd simple_maven_project
          mvn clean
        '''
      }
    }
        
    stage('Validate'){
      steps{
        sh '''
          mvn validate
        '''
      }
    }
        
    stage('Build'){
      steps{
        sh '''
          cd simple_maven_project
          mvn clean
        '''
      }
    }
        
  }
}