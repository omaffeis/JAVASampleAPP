pipeline {
    agent any
    stages {
        stage('Product Catalogue') {
            steps {
                echo 'Build Product Catalogue !'
                sh 'ls -l'
                sh 'cd productcatalogue'
                /*
                mvn package
                docker build . */
            }
        }
        stage('Build Shot Front') {
            steps {
                echo 'Build Shot Front !'
                /* cd shotfront
                 mvn build
                 docker build . */
            }
        }
        stage('Build Stock Manager') {
            steps {
                echo 'Build Stock Manager !'
                /* cd stockmanager
                 mvn build
                 docker build . */
            }
        }
    }
}
