pipeline {
    agent any
    stages {
        stage('Clonage du dépôt GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/theo-riou/Pipeline-test/'
            }
        }
        stage('Installation de Python 3.11 et pip') {
            steps {
                script {
                    // Mise à jour du système
                    sh 'sudo apt update'
                    // Installation de Python 3.11
                    sh 'sudo apt install -y python3.11 python3.11-distutils' 'python3-pip"
                }
            }
        }
        stage('Exécution du script Python') {
            steps {
                script {
                    // Exécution du script principal Python à partir du dépôt
                    sh 'python3.11 OSDetector.py'
                }
            }
        }
    }
}
