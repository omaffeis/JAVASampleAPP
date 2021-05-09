pipeline {
    agent {
        label 'Linux'
    }
    stages {
        stage('Product Catalogue') {
            steps {
                echo 'Build Product Catalogue !'
                sh 'env'
                sh 'cd productcatalogue; mvn package'
                // sh 'cd productcatalogue; docker build -t harbor.om-project/om-project/productcatalogue:v1 .'
                sh 'cd productcatalogue; docker build -tag omaffeis/productcatalogue:v1 .'
                sh 'cd productcatalogue; docker push omaffeis/productcatalogue:v1'
            }
        }
        stage('Build Shot Front') {
            steps {
                echo 'Build Shop Front !'
                sh 'cd shopfront; mvn package'
                sh 'cd shopfront ; docker build -tag omaffeis/shopfront:v1 .'
                sh 'cd shopfront ; docker push omaffeis/shopfront:v1'
            }
        }
        stage('Build Stock Manager') {
            steps {
                echo 'Build Stock Manager !'
                sh 'cd stockmanager; mvn package'
                sh 'cd stockmanager; docker build -tag omaffeis/stockmanager:v1 .'
                sh 'cd stockmanager; docker build omaffeis/stockmanager:v1'
            }
        }
    }
}
