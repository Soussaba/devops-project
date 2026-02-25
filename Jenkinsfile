pipeline {
    agent any

    stages {
        stage ('Clone'){
            steps{
                 git credentialsId: 'github-credentials' ,
                url: 'https://github.com/Soussaba/devops-project.git' ,
                branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat 'C:\\Users\\Administrateur\\AppData\\Local\\Programs\\Eclipse Adoptium\\jdk-17.0.18.8-hotspot\\bin\\javac" --version'
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
        success {
            echo 'Pipeline terminé avec succès !'
        }
        failure {
            echo ' Echec du pipeline '
        }
    }
}