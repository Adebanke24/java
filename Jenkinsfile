pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                sh ' cd SampleWebApp && mvn clean package'
                }
        }
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat_ID', path: '', url: 'http://3.149.252.114:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
