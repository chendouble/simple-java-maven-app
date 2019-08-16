pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
        }
    }
    stages {
        stage('Initialize'){
            def dockerHome = tool 'DefaultDocker'
            env.PATH = "${dockerHome}/bin:${env.PATH}"
        }
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}