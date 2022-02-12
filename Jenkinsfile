pipeline {

agent { node { label 'master' } }
tools {
        maven 'local_maven' 
        jdk 'local_jdk'
    }
stages {
    stage('Run in parallel') {
     parallel {
        stage('Code validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('Code Compile') {
            steps {
                sh 'mvn compile'
            }
        }
     }
    }
        stage('Code Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Code Package') {
            steps {
                sh 'mvn package'
            }
        }

        
    }
}
