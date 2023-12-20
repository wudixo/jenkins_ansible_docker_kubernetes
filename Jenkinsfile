pipeline {
  
    agent {
        label 'slavenode'
    }
    
    tools{
        maven "maven-3.9.6"
    }

    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/wudixo/jenkins_ansible_docker_kubernetes.git'
            }
        }
        stage('Build') {
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
