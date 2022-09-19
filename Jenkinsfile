node('built-in') 
{
    stage('ContinuousDownload') 
    {
        git 'https://github.com/srpandadevops211/mymaven.git'
    }
    stage('ContinuousBuild') 
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment') 
    {
        deploy adapters: [tomcat9(credentialsId: 'c9a30cae-bc7c-46b5-92df-de892bf449fe', path: '', url: 'http://172.31.86.137:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('ContinuousTesting') 
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/PipelineJob/testing.com'
    }
    
}
