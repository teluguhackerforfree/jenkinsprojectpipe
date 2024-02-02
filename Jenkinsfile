pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                git 'https://github.com/teluguhackerforfree/maven.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        
    stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'ff5975b8-2518-4217-9f0d-55c02bd36743', path: '', url: 'http://18.60.87.215:8081/')], contextPath: 'dataproapp', war: '**/*.war'
            }
        }
}
}
