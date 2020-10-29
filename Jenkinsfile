pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber() 
    
  }
 
  
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
        echo "current build number: ${currentBuild.number}"
       
        echo "${buildnum}"
        //slackSend channel: '#devops', message: 'this is a Test message  from build ${currentBuild.number}'
        //slackSend channel: '#devops', message: "${buildnum}"
      
      }
    }

  }
}
