pipeline {
    agent any

    stages {
        stage('Clone from Git') {
            steps {
                // Clone specific branch from Git
                git branch: 'main', url: 'https://github.com/19PA1A04B6/srikrishna.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
