pipeline {
    agent any
   
    stages {
        
        
        stage('Build') {
            steps {
                sh ''' #! /bin/bash
                
                mvn -Dmaven.test.failure.ignore=true install
               
                '''
            }
                }
      
      
}
}
