pipeline {
    agent any
    tools
    {
        maven 'Maven 3'
        jdk 'Java8'
    }
    stages {
        stage('clone'){
            steps{
                git credentialsId: '3accfb2a-2f7a-49b4-ab26-d87513ee81fb', url:
                'https://github.com/Laxmi99/myapp.git'
            }        }
            
            stage ('build'){
                steps {
                    sh 'mvn clean package'
                }
            }
            stage ('deploy'){
                steps{
                    sh "echo deploy success"
                }
            }
    }
}
