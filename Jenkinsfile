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
                    /*
                     * Multiline strings can be used for larger scripts. It is also possible to put scripts in your shared library
                     * and load them with 'libaryResource'
                     */
                      echo 'Develop branch'

//                     sh '
//                       docker build -t ${IMAGE} .
//                       docker tag ${IMAGE} ${IMAGE}:${VERSION}
//                       docker push ${IMAGE}:${VERSION}
//                         '
                }
            }
        }
    }
}
