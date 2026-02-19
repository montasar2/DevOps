pipeline {
    agent any  // exécute le pipeline sur n'importe quel agent disponible
    tools {
        maven 'M2_HOME'     
        jdk 'JAVA_HOME'      
    }
    stages {

        stage('Cloner GitHub') {
            steps {
                // Remplace ton URL par ton repo GitHub
                git branch: 'main', url: 'https://github.com/montasar2/DevOps.git'
            }
        }

        stage('Build avec Maven') {
            steps {
                // Nettoyer, compiler et package
                sh 'mvn clean package'
            }
        }

    } // fin de stages

    post {
        success {
            echo 'Pipeline terminé avec succès 🎉'
        }
        failure {
            echo 'Pipeline échoué ❌'
        }
    }
}
