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
                sh "sh 'python python_app.py'"
        }
}
    }
}