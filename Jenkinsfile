pipeline {
  agent any
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
        post {
       always {
           jiraSendDeploymentInfo environmentId: 'test', environmentName: 'test', environmentType: 'testing', serviceIds: [''], site: 'ajitsahu.atlassian.net', state: 'in_progress'
       }
      
      }
    }

  }
}
