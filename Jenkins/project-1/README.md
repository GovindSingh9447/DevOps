pipeline {
    agent any
    
    tools {
        jdk 'jdk11'
        maven 'maven3'
    }
     environment{
        SCANNER_HOME= tool 'Sonar-Scanner'
    }
   

    stages {
        stage('Git Checkout') {
            steps {
               git branch: 'main', changelog: false, poll: false, url: 'https://github.com/GovindSingh9447/Ekart.git'
            }
        }
        
        stage('Complie') {
            steps {
               sh "mvn clean compile"
            }
        }
        
        /*stage('Sonarqube') {
            steps {
                   sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.url=http://http://3.110.174.35:9000/ -Dsonar.login=squ_e292d7a3a5a6d91f12d2d0df937618cd72efc3fd -Dsonar.projectName=Ekart \
                   -Dsonar.java.binaries=. \
                   -Dsonar.projectKey=Ekart '''
               
            }
        }*/
        
         /*stage('OWASP SCAN') {
            steps {
               dependencyCheck additionalArguments: '--scan ./ ', odcInstallation: 'DP'
                dependencyCheckPublisher pattern: '**/  /*dependency-check-report.xml'
            }
        }*/
        
        stage('Build Application') {
            steps {
               sh "mvn clean install -DskipTests=true"
            }
        }
        
        stage('Build & Push Docker Image') {
            steps {
               script{
                   withDockerRegistry(credentialsId: 'docker-ranawattech', toolName: 'docker') {
                       sh "docker build -t ekart:latest -f docker/Dockerfile ."
                       sh "docker tag ekart:latest ranawattech/ekart:latest"
                       sh "docker push ranawattech/ekart:latest"
                   }
               }
            }
        }
        
        
    }
}
