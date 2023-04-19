pipeline {
    agent any
    stages {
        stage('git checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github-Credentials', url: 'https://github.com/narendra7306/sr-python-app.git']])
            }
        }
        stage('Build') {
            steps {
                git branch: 'master', url: 'https://github.com/narendra7306/sr-python-app.git'
                sh 'python3 -m ensurepip'
                sh 'python3 -m pip install flask'
                sh 'python3 main.py'
            }
        }
    }
}
   