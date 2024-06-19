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
                    reportName: "JaCoCo Report" //nazwa w jobie w jenkinsie,po lewej stornie zeby dzialalo trzeba:HTML Publisher w Jenkins
                ])
                sh "./gradlew jacocoTestCoverageVerification" //wywolanie bibloteki do weryfikacji kodu
            }
        }
        stage("Static code analysis") {
            steps {
                sh "./gradlew checkstyleMain" //wywolanie komendy do statycznej analizy kodu
                publishHTML(target: [
                    reportDir: 'build/reports/checkstyle/',
                    reportFiles: 'main.html',
                    reportName: "Checkstyle Report"
                ])
            }
        }
    }
}
