@Library('sharedlibrary')_
pipeline{
agent any
stages{
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
stage('Jenkins'){\
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



}

}
}