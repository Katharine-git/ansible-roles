pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                git 'https://github.com/Katharine-git/ansible-roles.git'
            }
        }
        stage('invoke ansible-playbook'){
            steps{
                ansiblePlaybook credentialsId: 'aws-private-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts.ini', playbook: 'roles.yml'
            }
        }
    }
}
