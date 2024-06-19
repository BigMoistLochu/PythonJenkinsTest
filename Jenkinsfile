pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/BigMoistLochu/PythonJenkinsTest', branch: 'main'
            }
        }
        stage("Env") {
            steps {
                sh 'ls'
        }
}
        stage("Compile") {
            steps {
                sh 'python python_app.py'
        }
}
    }
}
