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
                    sh 'sudo apt install -y python3.11 python3.11-distutils'
                    // Installation de pip pour Python 3.11
                    sh 'curl -sS https://bootstrap.pypa.io/get-pip.py | sudo python3.11'
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