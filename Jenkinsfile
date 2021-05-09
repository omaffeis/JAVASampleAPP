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
                sh 'cd productcatalogue; docker build --tag omaffeis/m2idocker-tp:v1'
                sh 'cd productcatalogue; docker push omaffeis/m2idocker-tp:v1'
                sh 'cd productcatalogue; docker build --tag harbor.om-project.fr/om-project/productcatalogue:v1 .'
                // sh 'cd productcatalogue; docker push harbor.om-project.fr/om-project/productcatalogue:v1'
            }
        }
        stage('Build Shot Front') {
            steps {
                echo 'Build Shop Front !'
                sh 'cd shopfront; mvn package'
                sh 'cd shopfront ; docker build --tag harbor.om-project.fr/om-project//shopfront:v1 .'
                // sh 'cd shopfront ; docker push harbor.om-project.fr/om-project//shopfront:v1'
            }
        }
        stage('Build Stock Manager') {
            steps {
                echo 'Build Stock Manager !'
                sh 'cd stockmanager; mvn package'
                sh 'cd stockmanager; docker build -tag harbor.om-project.fr/om-project/stockmanager:v1 .'
                // sh 'cd stockmanager; docker push harbor.om-project.fr/om-project/stockmanager:v1'
            }
        }
    }
}

