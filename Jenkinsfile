
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'YOUR_GITHUB_URL'
            }
        }

        stage('Install') {
            steps {
                bat 'python -m pip install -r requirements.txt'
            }
        }

        stage('Compile') {
            steps {
                bat 'python -m compileall app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m pytest -v'
            }
        }

        stage('Package') {
            steps {
                bat 'python -m zipfile -c app.zip app.py test_app.py requirements.txt'
            }
        }
    }
}
