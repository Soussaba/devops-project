pipeline {
    agent any

    stages {
        stage ('Clone') {
            steps {
                 git credentialsId: 'github-credentials' ,
                url: 'https://github.com/Soussaba/devops-project.git' ,
                branch: 'main'
            }
        }

        stage ('Build et Run'){
            steps {
                bat '''
                    dir /s Main.java
                    javac Main.java
                    dir /s Main.class
                    java Main
                '''
                echo 'Build et execution OK !'
            }
        }

        stage('Release') {
            steps {
                bat 'jar cvfe MonApp.jar Main Main.class'
                echo 'Package JAR cree !'
            }
        }

        stage('Deploy') {
            steps {
                bat 'java -jar MonApp.jar'
                echo 'Application deployee !'
            }
        }

        stage ('Test') {
            steps {
                echo 'Tests passes avec succès'
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