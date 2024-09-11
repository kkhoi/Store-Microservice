pipeline {
    agent any    
    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'shoppingapp', contextName: '', credentialsId: 'shoppingapp-token', namespace: 'shoppingapp', serverUrl: 'https://32E595DE73D4D5E340E0806FCC228D73.sk1.ap-southeast-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    sleep 30
                    sh "kubectl get svc -n shoppingapp"
                    
                }
            }
        }
    }
}
