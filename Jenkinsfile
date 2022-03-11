pipeline {
    agent any
    stages {
 stage ("Kubernetes Deploy") {
            steps {         
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f public-lb.yaml'
                sh 'kubectl apply -f private-lb.yaml'
                sh 'kubectl apply -f cluster-autoscaler.yaml'
                sh 'kubectl create -f namespace.yaml'
                sh 'kubectl create -f prometheus/'
                sh 'kubectl create -f grafana/'
                sh 'kubectl create -f nginx/'
                }
        }
 }
}
