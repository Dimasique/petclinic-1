pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Build and Publish Image') {
            when {
                branch 'develop'  //only run these steps on the master branch
            }
            steps {
                echo 'Develop branch'
            }
        }
        
    }
}
