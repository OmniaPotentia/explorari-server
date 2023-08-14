pipeline {
    agent any

    environment {
        NODE_VERSION = '18'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                // checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                // sh "curl -sL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash -"
                // sh "apt-get install -y nodejs"
                // sh "npm install"
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                // sh 'npm test'
            }
        }

        stage('Scan with SonarQube') {
            steps {
                script {
                    sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                    //def scannerHome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    /*withSonarQubeEnv('SonarQube Server') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }*/
                }
            }
        }

        stage('Build and Deploy') {
            steps {
                echo 'Building and deploying...'
                // sh 'npm run build'
                // Add deployment steps here (e.g., deploying to a server)
            }
        }
    }
}