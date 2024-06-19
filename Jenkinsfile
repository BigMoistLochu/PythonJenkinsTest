pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/BigMoistLochu/PythonJenkinsTest', branch: 'main'
            }
        }
        stage("Setup Python Environment") {
            steps {
                sh '''
                    # Update package list and install Python and virtualenv
                    apt-get update
                    apt-get install -y python3 python3-venv python3-pip
                '''
        }
}
        stage("Compile") {
            steps {
                sh 'python python_app.py'
        }
}
    }
}
