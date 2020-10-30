pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
    BUILD_STATUS = currentBuild.currentResult()
    //BUILD_STATUS=$(curl --silent ${BUILD_URL}api/json | jq -r '.result')
    
    gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    gitBranch = "*/master"
    
    SONARurl = 'http://13.64.108.228:9000'
    
    
    
  }


  stages {
    stage('TestBlaze') {
        
        parallel{
              
              stage ('1'){ 
                          steps {
                                echo " this is step a " 
                                slackSend channel: '#personal', message: 'this is a Test message from build ' + "${buildnum}"
                                }
                        }
              stage ('2'){ 
                          steps {
                                echo " this is step b " 
                                slackSend channel: '#personal', message: 'this is a Test message from build ' + "${buildnum}"
                                }
                        }

          
        } //Para end
      
      } // Stage end 
    
    stage('send email'){
      
      steps {
        mail bcc: '', body: '''build completed successfully . ${BUILD_STATUS} : Jenkins Build ${ buildnum}''', cc: '', from: '', replyTo: '', subject: '${BUILD_STATUS} : Jenkins Build ${ buildnum}', to: 'ajit.rsahu@gmail.com'
      }
      
    }//send email end 
    
  } // stages end
} // pipeline end 
