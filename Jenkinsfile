pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
    //status = currentBuild.getCurrentResult()
    //status2 = currentBuild.getResult()
    //BUILD_STATUS=$(curl --silent ${BUILD_URL}api/json | jq -r '.result')
    
   // gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    //gitBranch = "*/master"
    
    //SONARurl = 'http://13.64.108.228:9000'
    
    //TimeStamp = env.
    
    
    
  }


  stages {
    stage('TestBlaze') {
        
        def transitionInput =
    [
        transition: [
            id: '2'
        ]
    ]

    jiraTransitionIssue idOrKey: 'dev-4', input: transitionInput, site: 'jira'
      } // Stage end 
   
    
  } // stages end
} // pipeline end 
