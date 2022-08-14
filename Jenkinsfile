pipeline
{
    agent any
    stages
    {
       stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/Chintzxd/ganesh.git'
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline2/webapp/target/webapp.war ubuntu@172.31.23.167:/var/lib/tomcat9/webapps/testapp.war'
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline2/testing.jar'
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline2/webapp/target/webapp.war ubuntu@172.31.17.118:/var/lib/tomcat9/webapps/prodapp.war'
            }
        }
    }
}
