pipeline {
  agent any
 triggers {
 pollSCM('* * * * *')
 }

 stages {
 stage('Checkout') {
 steps {
 git branch: 'main', 
 url: 'https://github.com/sbgyhs/mywebapp'
 }
 }
 stage('Build') {
 steps {
 sh 'build'
 }
 }
 stage('Test') {
 steps {
 sh 'test'
 }
 }
 stage('Deploy') {
 steps {
 deploy adapters: [tomcat9(credentialsId: 'admin', url: '192.168.56.102:8080')],
contextPath: null, war: 'path/to/war'
 }
 }
 }
}
