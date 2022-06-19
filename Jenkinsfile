pipeline {
    agent any
    
    stages {
        stage('Master') {
            when { branch 'master' }
            steps {
               sh 'echo Master pipeline executed'
            }
        }

        stage('Develop') {
            when { branch 'develop' }
            steps {
               sh 'echo Develop pipeline executed'
            }
        }
    }
}
