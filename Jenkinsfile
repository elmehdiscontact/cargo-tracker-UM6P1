pipeline {
    agent any

    triggers {
        githubPush()   
    }
        tools {
    maven 'Maven'  // This name must match the name you configured in Jenkins
}

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/elmehdiscontact/cargo-tracker.git'
            }
        }

        stage('Build & Test with Coverage') {
            steps {
                bat 'mvn clean verify'
            }
        }

    
    }
//
    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
