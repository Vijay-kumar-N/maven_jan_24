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
    
    stage('Build'){
      steps{
        sh '''
          ls -lrt
          cd simple_maven_project
          ls -lrt
        '''
      }
    }
        
  }
}