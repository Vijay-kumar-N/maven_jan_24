pipeline{
  agent{
    label 'slave1'
  }

  stages{
    
    steps('Checkout'){
      checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: "https://github.com/Vijay-kumar-N/maven_jan_24.git", credentialsId: 'git_token']]    //credential for git repository
      ])
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