pipeline {
   agent { label ('ubuntu') }
    stages {
        stage('continuous-download') {
            steps {
             git 'https://github.com/rchidana/calcwebapp.git'
            }
        }
        stage ('continuous-build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('sonarqube'){
            steps{
             withSonarQubeEnv('SONAR-TOKEN') {
               sh 'mvn package sonar:sonar'
               }
            }
        }
    }
}