pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
    
    gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    gitBranch = "*/master"
    
  }
 
  tools { 
        maven 'maven' 
        jdk  'jdk'
    }
  
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
        echo "current build number: ${currentBuild.number}"
       
        echo "${buildnum}"
       
        //slackSend channel: '#devops', message: 'this is a Test message  from build ${currentBuild.number}'
        slackSend channel: '#personal', message: 'this is a Test message  from build ' + "${buildnum}"
      
      }
    }

    stage('Static-analysis') {
      steps {
        echo 'Static code Analysis'
        checkout([$class: 'GitSCM', branches: [[name: "${gitBranch}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: "${gitURL}"]]])
        withSonarQubeEnv(credentialsId: 'sonar', installationName: 'sonarqube')
          {sh 'mvn clean compile sonar:sonar -Dsonar.host.url=http://138.91.197.195:9000 -Dsonar.sources=. -Dsonar.tests=. -Dsonar.inclusions=**/test/java/servlet/createpage_junit.java -Dsonar.test.exclusions=**/test/java/servlet/createpage_junit.java -Dsonar.login=admin -Dsonar.password=admin' 
          }
        slackSend channel: '#personal', message: 'this is a Test message  from build finish ' + "${buildnum}"
      }
    } // Stage end

  } // stages end
} // pipeline end 
