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
                git 'https://github.com/ashokitschool/maven-web-app.git
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
