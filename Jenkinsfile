@Library('sharedlibrary')_
pipeline{
agent any
stages{











 
  stage('jira')
  {
    steps
    {
          jira_create_json(jsondata)
          log_function("JIRA","Project created")
          jira_create_issue_json(jsondata)
          log_function("JIRA","Issue created")
          jira_create_subtask_json(jsondata)
          log_function("JIRA","Subtask created")
          jira_add_comment1(jsondata)
          log_function("JIRA","Comment added")
          jira_collect_issue(jsondata)
          log_function("JIRA","Issue collected")
          jira_collect_particular_issue(jsondata)
          log_function("JIRA","Issue collected")
          jira_summary_of_project(jsondata)
          log_function("JIRA","Project summary collected")
          jira_get_comments_of_issue(jsondata)
          log_function("JIRA","Comments collected")
          //jira_delete_issue_json(jsondata)
          //jira_delete_project(jsondata)  
    }
    post
    {
      failure
      {
        log_function("JIRA","Failed")
      }
    }
  }

  
  
  
  
  
  
  stage("Confluence")
  {
  steps{
  confluenceConnectorSpaceJ(jsondata)
  log_function("Confluence","space created")
 
  confluencePrivateSpaceJ(jsondata)
  log_function("Confluence","Private space created")
 
  confluenceContentJ(jsondata)
  log_function("Confluence","Created a page")
 
  confluenceCollectorSpaceJ(jsondata)
  log_function("Confluence","Collected space info")
 
  confluenceGetGroupJ(jsondata)
  log_function("Confluence","Displayed all groups")
 
  confluenceGroupJ(jsondata)
  log_function("Confluence","particular group name details listed.")
 
  confluenceGroupMemberJ(jsondata)
  log_function("Confluence","Member details")
 
  confluenceDeleteContentJ(jsondata)
  log_function("Confluence","Deleted page by id")
  }
 
  post {
  failure
  {
  log_function("Confluence","failed")
  }
  }
} //stage end
  
  
  
  
  
  
  
  
stage('GITHUB')
   {
   steps
   {
   gitrepolist()
   log_function(" github ","collected repo list succesfully")
   gitrepo(jsondata)
   log_function(" github ","repo created succesfully")
   gitbranchlist(jsondata)
   log_function(" github ","collected branch list succesfully")
   gitbranch(jsondata)
   log_function(" github ","branch created succesfully")
   gitdeletebranch(jsondata)
   log_function(" github ","branch deleted succesfully")
   //gitdeleterepo(jsondata)
  log_function(" github ","Repo deleted succesfully")
   gitrepodetails(jsondata)
   log_function(" github ","collected repo details succesfully")
   githubcommit(jsondata)
   log_function(" github ","collected repo commits succesfully")
   }
   post{
    failure{
    log_function("GitHub failed")
    }}
   } 
   stage('GITLAB')
   {
   steps
   {
   gitlabrepolist()
   log_function(" gitlab ","collected project list succesfully")
    gitlabcreaterepo(jsondata)
    log_function(" gitlab ","projected created succesfully")
    gitlabbranchlist(jsondata)
    log_function(" gitlab ","collected branch list succesfully")
     gitlabbranch(jsondata)
     log_function(" gitlab ","branch created succesfully")
     gitlabcommit()
     log_function(" gitlab ","collected projects commits succesfully")
     gitlabbranchrmv(jsondata)
     log_function(" gitlab ","branch deleted succesfully")
     //gitlabprojremove(jsondata)
     log_function(" gitlab ","project deleted succesfully")
     gitlabprojectdetails()
     log_function(" gitlab ","collected gitlab project succesfully")
     }
     post{
    failure{
    log_function("GitLab failed")
    }}
     } 
  
  
  
  


  
stage('Jenkins'){
	steps{
			jenkins_createjob(jsondata)
			log_function("Jenkins","A new job created successfully")
			jenkins_deletejob("task1")
			log_function("Jenkins","Job deleted successfully")
			jenkins_renamejob("task","renamed_job")
			log_function("Jenkins","Job renamed successfully")
			jenkins_triggerbuild("create_job")
			log_function("Jenkins","Build triggered successfully")
			jenkins_schedulebuild("deletejob")
			log_function("Jenkins","Build scheduled successfully")
			jenkins_deletebuilds("paratest","106-116")
			log_function("Jenkins","Builds of given range in given job are deleted successfully")
			jenkins_disablejob("jobs")
			log_function("Jenkins","Job disabled successfully")
			jenkins_enablejob("test")
			log_function("Jenkins","job enabled successfully")
			jenkins_buildslist("FinalDemo")
			log_function("Jenkins","List of builds in given jobs fetched")
			jenkins_consoleoutput("FinalDemo")
			log_function("Jenkins","Console output of given build saved to consoleText in workspace")
			jenkins_pluginlist()
			log_function("Jenkins","List of installed plugins saved in workspace")
			jenkins_jobslist()
			log_function("Jenkins","List of jenkins jobs fetched")
			jenkins_lastbuildstatus("EDN250")
			log_function("Jenkins","Last build status of given job fetched successfully")
	}
	post
    {
      failure
      {
        log_function("JENKINS","Failed")
      }
    }
}




	
	
	
	
	
	
	stage('Bitbucket')
            {
                steps
                 {
                    Bbproject(jsondata)
                    log_function("Bitbucket","Project created successfully")
                    Bbrepo(jsondata)
                    log_function("Bitbucket","Repo created successfully")
                    Codepush(jsondata)
                    log_function("Bitbucket","Code is pushed successfully from Github")
                    Bbbranch(jsondata)
                    log_function("Bitbucket","Dev branch is created successfully")
                    Bbbranch1(jsondata)
                    log_function("Bitbucket","QA branch is created successfully")
                    Bbbranch2(jsondata)
                    log_function("Bitbucket","Prod branch is created successfully")
                    BBcollector(jsondata)
                    log_function("Bitbucket","All collector functions executed successfully")
             //     Bbdeletebranch2(jsondata)
              //    log_function("Bitbucket","Prod branch is deleted successfully")
              //    Bbdeleterepo(jsondata)
              //    log_function("Bitbucket","Repo is deleted successfully")
                  
            }
            post
    {
     failure
    {
     log_function("Bitbucket","Connector and Collector functions failed to execute")
    }
    }
           
            }  
	
	
	
	
	


stage('Bamboo')
            {
                steps
                {
                Bambooaddcomment(jsondata)
                log_function(" BAMBOO", "adding comment function executed successfully")
                Bambooaddlabelbuild(jsondata)
                log_function(" BAMBOO", "adding label function executed successfully")
                Bambooexecuteall(jsondata)
                log_function(" BAMBOO", "executing all stages function executed successfully")
                Bambootriggerdeploy(jsondata)
                log_function(" BAMBOO", "triggering deployment project function executed successfully")
                Bambooupdatedeployproject(jsondata)
                log_function(" BAMBOO", "name updation function in deployment project executed successfully")
                Bamboodeleteproject(jsondata)
                log_function(" BAMBOO", "delete project function executed successfully")
                Bamboocollectorall(jsondata)
                log_function(" BAMBOO", "collector functions executed successfully")
                }
                post
                {
                    failure
                    {
                       log_function("BAMBOO", "connector and collector functions  not executed successfully")
                    }
                }
              
            }




stage('SONARQUBE'){
            steps{
                sonarProject(jsondata)
                sonarParticularProject(jsondata)
                log_function("SONAR","Project created successfully")
                 sonarQualityGate(jsondata)
                log_function("SONAR","Quality Gate created successfully")
                sonarBlockerConditions(jsondata)
                log_function("SONAR","Blocker Conditions created")
                sonarCriticalConditions(jsondata)
                log_function("SONAR","Critical Conditions created")
                sonarAssociateProject()
                log_function("SONAR","Associating project with QualityGate successfully")
				sonarRemoveAssociation()
                log_function("SONAR","Removing the Association of a Project from a Quality Gate succesfully")
                //sonarSetAsDefault()
                //log_function("SONAR","Default Gate created successfully")
                sonarCollector()
                log_function("SONAR","Collected all the data from sonar server successfully")
                sonarParticularProjectData(jsondata)
                log_function("SONAR","Particular Project Data collected successfully")
                 sonarGateList()
                log_function("SONAR","Gate List displayed")
                 sonarDeleteQualityGate(jsondata)
                log_function("SONAR","QualityGate deleted successfully")
                sonarDeleteProject(jsondata)
                log_function("SONAR","Project deleted successfully")
                }  
             post{
               failure{
                  log_function("Sonarqube failure")
                      }
                  }
    }
	
	
	

stage('Nexus')
            {
                steps
                 { 
                   Ncreate_repo(jsondata) 
                   log_function("NEXUS","Repo created successfully")
                    Ncreate_user(jsondata)
                   log_function("NEXUS","User create successfully")
                    Nchange_pwd(jsondata)
                   log_function("NEXUS","Password changed successfully")
                    Ndown_artifact(jsondata)
                   log_function("NEXUS","Artifact downloaded successfully")
                     Npart_repo(jsondata)
                   log_function("NEXUS","Particulor repo details collected")
                     Nlist_repos(jsondata)
                   log_function("NEXUS","All repo details collected")
                     Nuserid_info(jsondata)
                   log_function("NEXUS","User id details collected")
                     Nrepo_status(jsondata)
                   log_function("NEXUS","Status of repo collected")
                     NPrivilage(jsondata)
                   log_function("NEXUS","security privileges retrived")
                    //Ndelete_repo(jsondata)
                 //log_function("NEXUS","Repo deleted successfully")
    }
    post
    {
    failure
    {
      log_function("NEXUS","CONNECTOR AND COLLECTOR FUNCTIONS NOT EXECUTED SUCCESSFULLY")
    }
    
                 }
    }
            

	
	
	
	
	stage('AZURE')
        {
            steps
            {
                create_project_json(jsondata)
                log_function("Azure", "Project created")
                storeoutput(jsondata)
                log_function("Azure", "Output stored")
                create_team_json(jsondata)
                log_function("Azure", "Team created")
                update_project_json(jsondata)
                 log_function("Azure", "Project Updated")
                col_p_pr_det(jsondata)
                log_function("Azure", "Particular Project Details Fetched")
               fetch_teams_org(jsondata)
                log_function("Azure", "Teams of an organisation Fetched")
               fetch_cntrl_org(jsondata)
                log_function("Azure", "Controllers Fetched")
               fetch_build_settings(jsondata)
                log_function("Azure", "Fetched Build Settings")
               fetch_build_list(jsondata)
                log_function("Azure", "Fetched Build list")
               fetch_team(jsondata)
                log_function("Azure", "Project Teams Fetched ")
             // delete_team(jsondata)
              //  log_function("Azure", "Project Team Deleted ")
             // delete_proj_json(jsondata)
                //log_function("Azure", "Project Deleted ")
			}            
				
	post
    {
      failure
      {
        log_function("Azure","Failed")
      }
    }
                
      }
	
	
	
	



}
}
