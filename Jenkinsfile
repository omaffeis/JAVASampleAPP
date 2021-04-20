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
    }
}