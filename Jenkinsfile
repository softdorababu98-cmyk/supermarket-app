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
                sh 'ansible-playbook /root/supermarket-app/deploy_tomcat.yml -i /opt/ansible/inventory.ini'
            }
        }
    }
}
