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
        stage("Code coverage") {
            steps {
                sh "./gradlew jacocoTestReport" //wywolanie bibloteki do analizy kodu ktora generuje plik w reportDir
                publishHTML (target: [
                    reportDir: 'build/reports/jacoco/test/html',
                    reportFiles: 'index.html',
                    reportName: "JaCoCo Report"
                ])
                sh "./gradlew jacocoTestCoverageVerification" //wywolanie bibloteki do weryfikacji kodu
            }
        }
    }
}
