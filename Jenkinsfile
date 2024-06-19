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
                    sudo apt-get update
                    sudo apt-get install -y python3 python3-venv python3-pip
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
