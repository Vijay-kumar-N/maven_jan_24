pipeline{
  agent{
    label 'slave1'
  }

  parameters{
    booleanParam(name: 'CLEAN', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'VALIDATE', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'COMPILE', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'TEST', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'PACKAGE', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'INTEGRATION_TEST', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'VERIFY', defaultValue: true, description: 'Toggle this value')
    booleanParam(name: 'INSTALL', defaultValue: true, description: 'Toggle this value')
    // booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Toggle this value')
  }

  stages{
    stage('Checkout'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: "https://github.com/Vijay-kumar-N/maven_jan_24.git", credentialsId: 'git_token']]])
      }
    }
    
    stage('Clean'){
      when{
        expression{
          params.CLEAN == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn clean   
        '''
      }
    }
        
    stage('Validate'){
      when{
        expression{
          params.VALIDATE == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn validate
        '''
      }
    }
        
    stage('Compile'){
      when{
        expression{
          params.COMPILE == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn compile
        '''
      }
    }
        
    stage('Test'){
      when{
        expression{
          params.TEST == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn test
        '''
      }
    }
        
    stage('Package'){
      when{
        expression{
          params.PACKAGE == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn package
        '''
      }
    }
        
    stage('Integration-test'){
      when{
        expression{
          params.INTEGRATION_TEST == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn integration-test
        '''
      }
    }
        
    stage('Verify'){
      when{
        expression{
          params.VERIFY == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn verify
        '''
      }
    }
        
    stage('Install'){
      when{
        expression{
          params.INSTALL == true
        }
      }
      steps{
        sh '''
          cd simple_maven_project
          mvn install
        '''
      }
    }
        
    // stage('Deploy'){
    //   when{
    //     expression{
    //       params.DEPLOY == true
    //     }
    //   }
    //   steps{
    //     sh '''
    //       cd simple_maven_project
    //       mvn deploy
    //     '''
    //   }
    // }
        
  }
}