pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.14.246.241:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
