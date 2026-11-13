
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/chandu1707/comp5.git'
            }
        }

      stage('Install') {
    steps {
        bat '"C:\\Users\\atmak\\AppData\\Local\\Programs\\Python\\Python37\\python.exe" -m pip install -r requirements.txt'
    }
}

     stage('Compile') {
    steps {
        bat '"C:\\Users\\atmak\\AppData\\Local\\Programs\\Python\\Python37\\python.exe" -m compileall app.py'
    }
}

     stage('Test') {
    steps {
        bat '"C:\\Users\\atmak\\AppData\\Local\\Programs\\Python\\Python37\\python.exe" -m pytest -v'
    }
}

        stage('Package') {
            steps {
                bat 'python -m zipfile -c app.zip app.py test_app.py requirements.txt'
            }
        }
    }
}
