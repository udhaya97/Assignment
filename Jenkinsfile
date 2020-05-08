def antVersion = 'Ant_1.10.7'
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    sh '$ANT_HOME/bin/ant'
                }
            }
        }
        stage('Test') { 
            steps {
                 sh 'make check'
                junit 'reports/**/*.xml'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'make publish'
            }
        }
    }
}


    
