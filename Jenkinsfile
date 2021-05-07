pipeline {
    agent any
    stages {
        stage('Product Catalogue') {
            steps {
                echo 'Build Product Catalogue !'
                sh 'cd productcatalogue; mvn package'
                // sh 'cd productcatalogue; docker build .'
            }
        }
        stage('Build Shot Front') {
            steps {
                echo 'Build Shop Front !'
                sh 'cd shopfront; mvn package'
                /* docker build . */
            }
        }
        stage('Build Stock Manager') {
            steps {
                echo 'Build Stock Manager !'
                sh 'cd stockmanager; mvn package'
                /* docker build . */
            }
        }
    }
}
