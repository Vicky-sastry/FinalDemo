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

}
}