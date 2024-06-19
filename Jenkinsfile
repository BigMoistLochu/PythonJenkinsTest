pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/BigMoistLochu/PythonJenkinsTest', branch: 'main'
            }
        }
        stage("Compile") {
            steps {
                sh 'python3 python_app.py'
            }
        }
        stage("Unit Tests") {
            steps {
                sh 'python3 python_app.py'
            }
        }
    }
}
