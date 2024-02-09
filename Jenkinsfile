pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'building'
                sh '''
                    ls
                    #ssh-keygen -f server
                    cat server.pub 
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
               echo'..' // ansiblePlaybook become: true, credentialsId: 'server-jenkins-to-deploy', disableHostKeyChecking: true, installation: 'ansible', inventory: '/root/.jenkins/workspace/hotel-web/ansible/inventory/hosts', playbook: '/root/.jenkins/workspace/hotel-web/ansible/playbook/install-apache-and-configure.yaml', vaultTmpPath: ''
            }
        }
    }
}