pipeline {
    agent any
    stages {
        stage('Clonage du dépôt GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/theo-riou/Pipeline-test/'
            }
        }
        stage('Compilation') {
            steps {
                script {
                    if (isUnix()) {
                    sh 'make' //Compilation Unix/Linux
                    } else {
                    bat 'make' // Compilation Windows
                    }
                }
            }
        }
        stage('Permissions') {
            when {
                expression { isUnix() } // Exécuter uniquement Unix
                }
            steps {
                sh 'chmod +x StringInverser' // Nom de l'executable
            }
         }

         stage('Nettoyage') {
             steps {
                 script {
                     if (isUnix()) {
                         sh 'make clean'
                     } else {
                         bat 'make clean'
                    }
                }
            }
        }
    }
}
