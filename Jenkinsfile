pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'building'
                sh '''
                ssh-keygen -f server -N '' -y

                '''
            }
        }

        stage('Test') {
            steps {
                echo 'testing'
            }
        }

        stage('Deploy') {
            steps {
                ansiblePlaybook become: true, credentialsId: 'server-jenkins-to-deploy', disableHostKeyChecking: true, installation: 'ansible', inventory: '/root/.jenkins/workspace/hotel-web/ansible/inventory/hosts', playbook: '/root/.jenkins/workspace/hotel-web/ansible/playbook/install-apache-and-configure.yaml', vaultTmpPath: ''
            }
        }
    }
}