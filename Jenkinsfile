pipeline {
agent any
tools {
maven 'apache-maven-3.5.2'
}
stages {
stage('Checkout') {
steps {
checkout scm
}
}
stage('Build') {
steps {
if(env.BRANCH_NAME == 'master'){
  echo 'Building..'
sh "mvn clean install"
archiveArtifacts artifacts: '**/*.war', onlyIfSuccessful: true
}
}
}
stage('Test') {
steps {
echo 'Testing..'
}
}
stage('Deploy') {
steps {
echo 'Deploying....'
}
}
}
}
