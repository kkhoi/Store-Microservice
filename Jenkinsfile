pipeline {
    agent any    
    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'shoppingapp', contextName: '', credentialsId: 'shoppingapp-token', namespace: 'shoppingapp', serverUrl: 'https://78394C5715F7EC6249E64B992D0692BB.gr7.ap-southeast-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    sleep 35
                    sh "kubectl get svc -n shoppingapp"
                    
                }
            }
        }
    }
}
