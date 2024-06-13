pipeline {
    agent any
    environment {
        name='Sabzar'
    }
    stages {
        stage('Test') {
            steps {
                echo 'Code Test Stage '
                sh 'date'
                sh 'pwd'
                sh ' echo $name'
            }
        }
         stage('Sonar') {
            steps {
                echo 'Sonar validation Stage'
                sh '''
                    ls
                    date
                    pwd
                    whoami
                   echo $name
                '''
            }
        }
         stage('Build') {
            steps {
                echo 'Build Stage'
                sh 'echo $name'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy Stage'
               sh '''
                    echo $BUILD_ID
                    echo $name
                 
                  '''    
            }
        }
    }
    post {
        always {
            echo 'this is always run'
        }
        failure {
            mail to: 'sabzar.raja@gmail.com' , subject: 'The Pipeline failed', body: "jOB #BUILD_ID Failed" 
            }
        success {
            echo" Success"
        }
    }
}
