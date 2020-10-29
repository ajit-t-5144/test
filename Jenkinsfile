pipeline {
  agent any
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
        echo "current build number: ${currentBuild.number}"
        //slackSend channel: '#devops', message: 'this is a Test message  from build ${currentBuild.number}'
      
      }
    }

  }
}
