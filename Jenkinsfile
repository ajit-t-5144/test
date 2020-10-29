pipeline {
  agent any
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
         slackSend channel: '#devops', message: 'this is a Test message  from build ${currentBuild.number}'
      
      }
    }

  }
}
