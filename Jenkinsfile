pipeline{
    agent { label 'jenkins-agent'}
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }

    stages{
        stage ("cleanup Workspace"){
            steps {
                cleanWs()
            }
        }

        stage ("checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/pavi56/register-app' 
            }
        }

        stage ('Build Application'){
            steps {
                sh "mvn clean package"
            }
        }

        stage ("Test Appliccation"){
            steps {
                sh "mvn test"
            }
        }
    }
}