pipeline {
    agent any

    stages {
        stage ('Clone'){
            steps{
                git credentialsID: 'githubcredentiials',
                url: 'https://github.com/Soussaba/DevOpsProject.git' ,
                branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat 'javac --version'
                echo 'Build Java OK'
            }
        }

        stage('Test') {
            steps {
                echo 'Test à venir...'
            }
        }

    }

    post {
        sucess {
            echo 'Pipeline terminé avec succès !'
        }
        failure {
            echo ' Echec du pipeline '
        }
    }
}