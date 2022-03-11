pipeline {
    agent any
    stages {
 stage ("Kubernetes Export") {
            steps {         
                 sh 'aws eks --region eu-west-3 update-kubeconfig --name demo || true'
            }
        }
 stage ("Kubernetes Deploy") {
            steps {         
                sh 'kubectl apply -f deployment.yaml || true'
                sh 'kubectl apply -f public-lb.yaml || true'
                sh 'kubectl apply -f private-lb.yaml || true'
                sh 'kubectl apply -f cluster-autoscaler.yaml || true'
                sh 'kubectl create -f namespace.yaml || true'
                sh 'kubectl create -f prometheus/ || true'
                sh 'kubectl create -f grafana/ || true'
                sh 'kubectl create -f nginx/ || true'
                }
        }
        
    }
}
