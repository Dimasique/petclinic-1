pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing..'
                sh './mvnw test'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh './mvnw build'
            }
        }
        stage('Push to registry') {
            steps {
                echo 'Pushing..'
                sh 'mv target/*.jar app.jar'
            }
        }
        stage('Deploy') {
            when {
                branch 'main'  //only run these steps on the main branch
            }
            steps {
                echo 'Deploying....'
                sh 'java -jar app.jar'
            }
        }        
    }
}
