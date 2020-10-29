pipeline {
  agent any
  stages {
    stage('TestBlaze') {
      steps {
        echo 'Blazemetertest'
        blazeMeterTest(credentialsId: 'blazemeter', workspaceId: '680689', testId: '8642591.taurus')
      }
    }

  }
}