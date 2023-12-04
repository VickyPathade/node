pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main', url: 'https://github.com/VickyPathade/node.git'
            }
        }
         stage('build') {
            steps {
                script {
                    sh 'docker build -t vicky/notes-app .'
                }
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
               script {
                    sh 'kubectl apply -f deployment.yml'
                    
                }
            }
        }
    }
}
