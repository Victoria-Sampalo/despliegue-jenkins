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
                COPY . /var/www/html/
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
