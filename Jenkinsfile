pipeline{
    agent{
        label "master"
    }
    stages{
        stage("Build ShopFront"){
            steps{
                sh '''
                echo "========Build ShopFront========"
                cd ./shopfront
                mvn clean install
                '''
            }
        }
        stage("Build Product Catalogue"){
            steps{
                sh '''
                echo "========Build Product Catalogue========"
                cd ./productcatalogue
                mvn clean install
                '''
            }
        }
        stage("Build Stock Manager"){
            steps{
                sh '''
                echo "========Build Stock Manager========"
                cd ./stockmanager
                mvn clean install
                '''
            }
        }
        stage("Docker Build Shopfront"){
            steps{
                sh '''
                echo "====Build Shopfront===="
                cd ./shopfront
                docker login -u jmeunierilki -p xao672JMxao672JM
                docker build -t jmeunierilki/shopfront:1.0 .
                docker push jmeunierilki/shopfront:1.0
                '''
            }
        }
        stage("Docker Build Product Catalogue"){
            steps{
                sh '''
                echo "====Build Product Catalogue===="
                cd ./productcatalogue
                docker login -u jmeunierilki -p xao672JMxao672JM
                docker build -t jmeunierilki/productcatalogue:1.0 .
                docker push jmeunierilki/productcatalogue:1.0
                '''
            }
        }
        stage("Docker Build Stock Manager"){
            steps{
                sh '''
                echo "====Build Stock Manager===="
                cd ./stockmanager
                docker login -u jmeunierilki -p xao672JMxao672JM
                docker build -t jmeunierilki/stockmanager:1.0 .
                docker push jmeunierilki/stockmanager:1.0
                '''
            }
        }
        stage("Kubernetes Deploy"){
            steps{
                sh '''
                echo "====++++executing Kubernetes Deploy++++===="
                kubectl apply -f ./kubernetes/shopfront-service.yaml --kubeconfig /home/jenkins/kubeconfig.yaml
                kubectl apply -f ./kubernetes/productcatalogue-service.yaml --kubeconfig /home/jenkins/kubeconfig.yaml
                kubectl apply -f ./kubernetes/stockmanager-service.yaml --kubeconfig /home/jenkins/kubeconfig.yaml

                '''
            }
        }
    }
}