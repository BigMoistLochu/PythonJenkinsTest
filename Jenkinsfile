pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/BigMoistLochu/PythonJenkinsTest', branch: 'main'
            }
        }
        stage("Check") {
            steps {
                sh ls
        }
        stage("Compile") {
            steps {
                sh python python_app.py
        }
}
    }
}
