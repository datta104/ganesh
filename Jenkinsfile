/* pipeline
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
*/

pipeline{

agent any
	
tools {
  maven 'maven-3.8.7'
}
   
stages{
    stage('CheckOutCode'){
        steps{
            git 'https://github.com/Chintzxd/ganesh.git'
	}
  }
    stage('version') {
      steps {
        sh 'python --version'
      }
    }
    stage('hello.py') {
      steps {
	git 'https://github.com/Chintzxd/ganesh.git'
        sh 'python hello.py'
      }
    }
   stage('shell') {
      steps {
        sh 'sh odd.sh'
      }
    }
   stage('maven') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
