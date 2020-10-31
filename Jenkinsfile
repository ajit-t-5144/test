pipeline {
  agent any
  
  environment {
    
    buildnum = currentBuild.getNumber()
   // status = currentBuild.getCurrentResult()
    //status2 = currentBuild.getResult()
    //BUILD_STATUS=$(curl --silent ${BUILD_URL}api/json | jq -r '.result')
    
   // gitURL = "https://github.com/ajit-t-5144/DevOps-Demo-WebApp.git"
    //gitBranch = "*/master"
    
    //SONARurl = 'http://13.64.108.228:9000'
    
    //TimeStamp = env.BUILD_TIMESTAMP
    
    transition = jiraGetIssueTransitions idOrKey: 'dev-4', site: 'jira'
    transition2 = jiraGetIssueTransitions idOrKey: 'dev-2', site: 'jira'
    
    //transitionInput = transition id: '11'
    
  }


  stages {
    stage('TestBlaze') {
        
        parallel{
              
              stage ('1'){ 
                          steps {
                                echo " this is step a " 
                                //slackSend channel: '#personal', message: 'this is a Test message from build ' + "${buildnum}"
                                //echo "${BUILD_TIMESTAMP}"
                                }
                        }
              stage ('2'){ 
                          steps {
                                echo " this is step b " 
                                //slackSend channel: '#personal', message: "${currentBuild.currentResult}" + 'this is a Test message from build ' + "${buildnum}" + "${BUILD_TIMESTAMP}"
                                // echo "${BUILD_TIMESTAMP}"
                                //jiraAddComment comment: '"hello World"', idOrKey: 'dev-2', site: 'jira'
                                
                            
                            echo "${transition}"
                              echo "${transition2}"
                            
                               // jiraTransitionIssue idOrKey: 'dev-4', input: transitionInput, site: 'jira'
                                //jiraSendBuildInfo branch: '', site: 'ajitsahu.atlassian.net', idOrKey: 'dev-2'
                                //jiraSendDeploymentInfo environmentId: 'test', environmentName: '', environmentType: 'development', serviceIds: [''], site: 'ajitsahu.atlassian.net', state: 'in_progress'
                                }
                        }

          
        } //Para end
      
      } // Stage end 
   
    
  } // stages end
} // pipeline end 
