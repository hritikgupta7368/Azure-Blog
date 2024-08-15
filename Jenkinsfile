pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-blog-app .'
            }
        }
        
        stage('Test') {
            steps {
                sh 'docker run my-blog-app python -m unittest discover tests'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f kubernetes-manifests/'
            }
        }
    }
}