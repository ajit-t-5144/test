pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
    status = currentBuild.getCurrentResult()
    status2 = currentBuild.getResult()
    //BUILD_STATUS=$(curl --silent ${BUILD_URL}api/json | jq -r '.result')
    
    gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    gitBranch = "*/master"
    
    SONARurl = 'http://13.64.108.228:9000'
    
    //TimeStamp = env.BUILD_TIMESTAMP
    
  }


  stages {
    stage('TestBlaze') {
        
        parallel{
              
              stage ('1'){ 
                          steps {
                                echo " this is step a " 
                                slackSend channel: '#personal', message: 'this is a Test message from build ' + "${buildnum}"
                                echo "${BUILD_TIMESTAMP}"
                                }
                        }
              stage ('2'){ 
                          steps {
                                echo " this is step b " 
                                slackSend channel: '#personal', message: "${currentBuild.currentResult}" + 'this is a Test message from build ' + "${buildnum}" + "${BUILD_TIMESTAMP}"
                                 echo "${BUILD_TIMESTAMP}"
                                jiraAddComment comment: 'Hello World ', idOrKey: 'DEV-2', site: 'ajitsahu.atlassian.net'
                                }
                        }

          
        } //Para end
      
      } // Stage end 
   
    
  } // stages end
} // pipeline end 
