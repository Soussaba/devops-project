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

        stage ('Build'){
            steps {
                bat 'javac Main.java'
                echo 'Compilation Java OK'
            }
        }

        stage ("Run"){
            steps {
                bat 'java -cp . Main'
                echo 'Execution Java OK !'
            }
        }

        stage('Release'){
            steps {
                bat 'jar cvf MonApp.jar Main.class'
                echo 'Package JAR cree !'
            }
        }

        stage('Deploy') {
            steps {
                bat 'java -jar MonApp.jar'
                echo 'Application deployee !'
            }
        }

        stage ('Test'){
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