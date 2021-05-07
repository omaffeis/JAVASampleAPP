pipeline {
    agent {
        label 'Linux'
    }
    stages {
        stage('Product Catalogue') {
            steps {
                echo 'Build Product Catalogue !'
                sh 'cd productcatalogue; mvn package'
                sh 'cd productcatalogue; docker build .'
            }
        }
        stage('Build Shot Front') {
            steps {
                echo 'Build Shop Front !'
                sh 'cd shopfront; mvn package'
                sh 'cd shopfront; docker build .'
            }
        }
        stage('Build Stock Manager') {
            steps {
                echo 'Build Stock Manager !'
                sh 'cd stockmanager; mvn package'
                sh 'cd stockmanager; docker build .'
            }
        }
    }
}
