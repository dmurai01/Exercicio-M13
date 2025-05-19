pipeline {
    agent any
    
    tools {nodejs "NodejsIstall"}
    
    stages {
        stage('Setup') {
            steps {
                git branch: 'main', url: 'https://github.com/dmurai01/Exercicio-M13.git'
            }
        }
        stage('Rodar Serverest') {
            steps {
               bat '''set NO_COLOR=1
start npx serverest'''
            }
        }
        stage('Test') {
            steps {
                bat 'newman run Exercicio-M13.postman_collection.json -e workspace.postman_globals.json'
            }
        }        
    }
}
