pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Copiando los ficheros'
                sh 'npm install'
                sh 'npm run build'                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo 'Copiando los ficheros hasta la ruta de despliegue'
                sh 'npm install -g serve'
            }
        }
        stage('Execute'){
            steps{
                echo 'Executing...'
                sh 'serve -s build -l 3000'
            }
        }
    }
}
