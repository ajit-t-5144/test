//this is define section 

def transitionInput = [transition: [id: '11']]
def serviceid = [serviceIds: [id: 'DEV-4']]
//def association = [Association{associationType=serviceIdOrKeys: ['DEV-4']}]

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
    transitionx = jiraGetIssueTransitions idOrKey: 'dev-2', site: 'jira'
    
    transition2 = transitionx.data.toString()
    
   
    
    
    
  }

  tools{
        groovy 'groovy'  
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
                                
                            
                            //echo "${transition}"
                            //def transitionInput = [transition: [id: '11']]
                            //  echo "${transition2}"
                            
                            //echo "${transition}.data.toString()"
                            
                              //jiraTransitionIssue idOrKey: 'dev-4', input: transitionInput, site: 'jira'
                            
                            //jiraSendBuildInfo branch: '', site: 'jira'
                                //jiraSendBuildInfo branch: '', site: 'ajitsahu.atlassian.net', idOrKey: 'dev-2'
                            //jiraSendDeploymentInfo environmentId: 'test', environmentName: '', environmentType: 'development', serviceIds: [''], site: 'ajitsahu.atlassian.net', state: 'in_progress'
                                }
                  post{
                      always{
                        jiraSendDeploymentInfo environmentId: 'us-stg-1', environmentName: 'devops-demo', environmentType: 'testing', serviceIds: ['DEV-4'], site: 'ajitsahu.atlassian.net', state: 'in_progress'
                      //jiraSendBuildInfo branch: "${branchName}", site: 'ajitsahu.atlassian.net'
                         //jiraSendDeploymentInfo site: 'ajitsahu.atlassian.net', serviceIds: ['DEV-4'],environmentId: 'us-prod-1', environmentName: 'us-prod-1', environmentType: 'production'
                        //jiraSendDeploymentInfo site: 'ajitsahu.atlassian.net' , environmentId: 'developement', environmentName: 'test-1', environmentType: 'testing', state: 'in_progress'
                         }
                  }
                        }

          
        } //Para end
      
      } // Stage end 
   
    
  } // stages end
} // pipeline end 
