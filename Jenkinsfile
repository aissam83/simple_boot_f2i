
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
    }
}
