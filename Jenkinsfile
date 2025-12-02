pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/softdorababu98-cmyk/supermarket-app.git'  
           }
        }
        stage('Deploy to Tomcat with Ansible') {
            steps {
                sh 'ansible-playbook deploy_tomcat.yml -i inventory.ini'
            }
        }
    }
}
