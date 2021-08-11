pipeline{

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_KEY')
    }

    agent any
    stages {
        stage('checkout') {
            steps {
                
                git 'https://github.com/Katharine-git/ansible-roles.git'
            }
        }  
        stage('invoke ansiblle-playbook'){
            steps{
                ansiblePlaybook credentialsId: 'aws-private-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts.ini', playbook: 'roles.yml'
            }
        
        }
        
    }
}
