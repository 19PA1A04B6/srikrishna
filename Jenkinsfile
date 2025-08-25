pipeline {
    agent any

    stages {
        stage('Clone from Git') {
            steps {
                // Clone specific branch from Git
                git branch: 'main', url: 'https://github.com/19PA1A04B6/srikrishna.git'
            }
        }

        stage('Setup Virtual Env & Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    if [ -f requirements.txt ]; then
                        pip install -r requirements.txt
                    fi
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                    . venv/bin/activate
                    python app.py
                '''
            }
        }
    }
}
