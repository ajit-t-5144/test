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
              
              stage ('1'){ steps {echo " this is step a "}}
              stage ('2'){ steps {echo " this is step b "}}
              stage ('3'){ steps {echo " this is step c"}}
          
        } //Para end
      slackSend channel: '#personal', message: 'this is a Test message  from build ' + "${buildnum}"
      } // Stage end 
    
  } // stages end
} // pipeline end 
