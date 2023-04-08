pipeline {
    agent any

    stages {
        stage('git clone') {
            steps {
                git 'https://github.com/Anudeepkumar02/faber.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Artifact') {
            steps {
                sh 'aws s3 cp target/*.war s3://warfileswebproject/faber/faber.war'
                sh 'aws s3 cp target/*.war s3://warfileswebproject/faber/faber$BUILD_NUMBER.war'
            }
        }
    }
}
