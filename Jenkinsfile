pipeline{
  agent{
    label 'slave1'
  }

  parameters{
    booleanParam(name: 'CLEAN', defaultValue: true, description: 'Toggle this value')
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
      steps{
        sh '''
          cd simple_maven_project
          mvn validate
        '''
      }
    }
        
    stage('Compile'){
      steps{
        sh '''
          cd simple_maven_project
          mvn compile
        '''
      }
    }
        
    stage('Test'){
      steps{
        sh '''
          cd simple_maven_project
          mvn test
        '''
      }
    }
        
    stage('Package'){
      steps{
        sh '''
          cd simple_maven_project
          mvn package
        '''
      }
    }
        
    stage('Integration-test'){
      steps{
        sh '''
          cd simple_maven_project
          mvn integration-test
        '''
      }
    }
        
    stage('Verify'){
      steps{
        sh '''
          cd simple_maven_project
          mvn verify
        '''
      }
    }
        
    stage('Install'){
      steps{
        sh '''
          cd simple_maven_project
          mvn install
        '''
      }
    }
        
    // stage('Deploy'){
    //   steps{
    //     sh '''
    //       cd simple_maven_project
    //       mvn deploy
    //     '''
    //   }
    // }
        
  }
}