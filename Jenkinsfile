pipeline {
  agent any
  tools {
    jdk 'java'
    maven 'maven'
      }
      stages{
        stage('Clone') {
          steps {
            git 'https://github.com/Laxmi99/docker.git'
          }
        }
        stage('Build') {
          steps {
            sh 'mvn clean package'
          }
        }
        stage('Sonar-Publish') {
          steps {
            sh 'mvn sonar:sonar -Dsonar.host.url=http://13.233.128.137:9000// -Dsonar.login=20f76b1f96f459ee0b39b32c221cbc8814fc3025'
          }
        }
        stage('Docker-Build') {
          steps {
            sh 'docker build -t laxmi99/docker:1.0.0'
        }
      }
        stage('Docker-Push') {
          steps {
            sh 'docker push laxmi99/docker:1.0.0'
        }
      }
        stage('Docker-Run') {
          steps {
            sh 'ssh -o "StrictHostKeyChecking=no" -i /home/centos/key.pem centos@13.233.253.190 sudo docker run -it -p 8081:8080 -d --name mydocker laxmi99/docker:1.0.0'
        }
      }
      }  
}
