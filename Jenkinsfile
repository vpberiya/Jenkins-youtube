pipeline {
    agent any
    environment {
        name = 'VB'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    }
    stages {
        stage('Run as command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Environment'){
            steps{
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
            }
        }
        stage('Parameters'){
            steps{
                sh 'echo "${PERSON}"'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
        stage('Deploy-test') {
            steps {
                echo 'Deploy on test'
            }
        }
        stage('Continue ?') {
            input{
                message "Should we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy-prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo "Failure"
        }
        success {
            echo "Success"
        }
    }
}
