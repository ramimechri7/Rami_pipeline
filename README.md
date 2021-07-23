pipeline {
    agent any
    stages {



        stage('build') {
            steps{
                    tool name: 'Maven_3_8_1', type: 'maven'
                    sh 'mvn clean compile'
            }
        }


        stage('test') {
                    steps{

                            sh 'mvn test'
                    }
        }
        stage('deploy') {
                    steps{

                            sh 'mvn deploy'
                    }
        }


    }
}
