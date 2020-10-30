pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
    
    gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    gitBranch = "*/master"
    
    SONARurl = 'http://13.64.108.228:9000'
    
    
    
  }

  
  stages {
    stage('TestBlaze') {
      steps {
        echo 'send jira deployment'
        echo "current build number: ${currentBuild.number}"
       
        echo "${buildnum}"
        
        echo " sonar host url is ${SONARurl}"
       
        //slackSend channel: '#devops', message: 'this is a Test message  from build ${currentBuild.number}'
        slackSend channel: '#personal', message: 'this is a Test message  from build ' + "${buildnum}"
      
      }
    }

    //Parallel Stage Start 
    stages {
      
      steps {
            parallel(
              
              a: { echo " this is step a "},
              b: { echo " this is step b "},
              c: { echo " this is step c "}
            )
      }
    } // Parallel Stage end 

  } // stages end
} // pipeline end 
