pipeline {
    
    agent {
         label 'ansible-node'
    }
    
    tools{
        maven 'maven'
    }

    stages {
        stage('Git Clone') {
            steps {
                git 'https://github.com/wudixo/jenkins_ansible_docker_kubernetes'
            }
        }
        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Create Image'){
            steps{
               steps {
                	script {
                		sh 'ansible-playbook task.yml'
                	}
                }
            }
        }
    }
}
