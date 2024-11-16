pipeline {
    agent any
    stages {
        stage('Download-Code-GIT') {
            steps {
                echo "Download code from git"
                git branch: 'main', url: 'https://github.com/devopstechlab/maven-jenkins4.git'
            }
        }
        stage('Build') {
            steps {
        sh '''docker build -t devopstechlab/webapp:v${BUILD_NUMBER} .
            docker tag devopstechlab/webapp:v${BUILD_NUMBER} devopstechlab/webapp:latest 
            docker push devopstechlab/webapp:v${BUILD_NUMBER}
            docker push devopstechlab/webapp:latest '''
            }
        }
    }
}
