pipeline{
    agent{
        label "master"
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                echo "========Build Maven========"
                cd ./shopfront
                mvn clean install
                '''
            }
        }
        stage("Docker Build"){
            steps{
                sh '''
                echo "====Build Docker===="
                cd ./shopfront
                docker login -u jmeunierilki -p xao672JMxao672JM
                docker build -t jmeunierilki/shopfront:1.0 .
                docker push jmeunierilki/shopfront:1.0
                '''
            }

        }
    }
}