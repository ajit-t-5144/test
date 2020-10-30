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
        
        parallel{
              
              stage ('1'){ 
                          steps {
                                echo " this is step a " 
                                slackSend channel: '#personal', message: 'this is a Test message  from build ' + "${buildnum}"
                                }
                        }
              stage ('2'){ 
                          steps {
                                echo " this is step b " 
                                slackSend channel: '#personal', message: 'this is a Test message  from build ' + "${buildnum}"
                                }
                        }

          
        } //Para end
      
      } // Stage end 
    
  } // stages end
} // pipeline end 
