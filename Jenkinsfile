
pipeline {
    agent any
    tools {
        maven 'M3'
    }
    stages {
        stage('checkout') {
        steps {
            git url :'https://github.com/aissam83/simple_boot_f2i.git'
              } 
        }

         stage('compile') {
            steps {
            sh 'mvn clean compile'
            }
        }
        stage('Test') {
        steps {
            sh 'mvn test'
            }
        }
        stage('Package') {
        steps {
            sh 'mvn package'
            }
        }
         stage('Buil docker image') {
        steps {
            sh 'docker -H 192.168.33.20:2375 build -t simple-boot .'
            }
        }
        stage('Run docker container') {
        steps {
            sh 'docker -H 192.168.33.20:2375 run -d --name=simple-boot -p 8080:8080 simple-boot'
            }
        }
    }
}
