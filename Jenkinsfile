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
      
      
}
}
