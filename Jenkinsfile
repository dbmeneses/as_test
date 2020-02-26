pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'git rev-parse origin/$BRANCH_NAME'
                echo 'Building..'
                sh 'env'
                sh 'wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.2.0.1873-linux.zip'
                sh 'unzip sonar-scanner-cli-4.2.0.1873-linux.zip'
                sh 'sonar-scanner-4.2.0.1873-linux/bin/sonar-scanner -Dsonar.projectKey=github'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
       post { 
        always { 
            cleanWs()
        }
    }
}
