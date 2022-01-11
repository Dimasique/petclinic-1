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
                sh './mvnw package'
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
                sh 'java -Dserver.port=8083 -jar app.jar'
            }
        }        
    }
}
