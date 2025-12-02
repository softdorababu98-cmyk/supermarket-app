pipeline {
    agent any
    
    stages {
        stage('Deploy to Tomcat') {
            steps {
                sh 'ansible-playbook deploy_tomcat.yml -i inventory.ini'
            }
        }
    }
    
    post {
        success {
            echo '✅ Supermarket app deployed successfully to 192.168.154.131:8080!'
        }
        failure {
            echo '❌ Deployment failed!'
        }
    }
}

