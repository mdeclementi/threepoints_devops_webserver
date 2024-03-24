@Library('threepoints-sharedlib@master') _
pipeline {
agent any
stages { stage('Checkout') {
steps {
git branch: 'master', credentialsId: 'secret-user', url:
'https://github.com/mdeclementi/threepoints_devops_webserver.git' }
}
stage('Pruebas de SAST') { steps {
script {
sonarAnalysis(false) }
} }
        stage('Build') {
            steps {
sh 'docker build -t devops_threepoints:latest .' }
} }
   
post {
        success {
echo 'Pipeline exitosa' }
failure {
echo 'Pipeline fallida'
} }
}
