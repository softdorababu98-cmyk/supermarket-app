pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                sh 'ansible-playbook deploy_tomcat.yml -i inventory.ini'  // ← FIXED: Added sh
            }
        }
    }
    
    post {
        success {
            echo '✅ Supermarket app deployed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}

