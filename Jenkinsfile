pipeline {
    agent any
   
    stages {
        stage('Clone Repository') {
            steps {
                sh ''' #! /bin/bash
                git 'https://github.com/vijaytammisetti/hellow-world.git'
          
                '''
                }
        }
        
        stage('Build') {
            steps {
                sh ''' #! /bin/bash
                
                mvn -Dmaven.test.failure.ignore=true install
               
                '''
            }
                }
      
        stage('Sonarqube') {
            environment {
                scannerHome = tool 'sonarScanner'
                }
            steps {
                withSonarQubeEnv('sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
                timeout(time: 5, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
       
    post {
        always {
            echo 'Stage is success'
        }
    }
}
}
