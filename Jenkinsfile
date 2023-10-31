pipeline {
   agent any
   
    stages {
        stage('Checkout') {
            steps {
                 git url: 'https://github.com/Anliza/testing', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh '''
                        python3 -m venv venv
                        . venv/bin/activate
                        pip install --upgrade pip
                        pip install -r requirements.txt
                    '''
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh '. venv/bin/activate && pytest'
                }
            }
        }
    }
}