

@Library('mylibrary')_
pipeline
{
    agent any
    stages
    {
        stage('ContDownload_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('ContBuild_Master')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()
                }
            }
        }
        stage('ContDeployment_Master')
        {
            steps
            {
                script
                {
                    cicd.tomcatDeploy("DeclarativePipleinewithSharedLibraries","172.31.95.118","testapp")
                }
            }
        }
        stage('ContTesting_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.executeSelenium("DeclarativePipleinewithSharedLibraries")
                }
            }
        }
        stage('ContDelivery_Master')
        {
            steps
            {
                script
                {
                    cicd.tomcatDeploy("DeclarativePipleinewithSharedLibraries","172.31.90.70","prodapp")
                }
            }
        }
        
        
        
        
        
        
        
        
        
    }
}
