pipeline {
    agent {
    kubernetes {
        label podlabel
        yaml """
kind: Pod
metadata:
  name: jenkins-slave
spec:
  containers:
  - name: maven
    image: maven:3-alpine
    imagePullPolicy: Always
"""
   }
}
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}