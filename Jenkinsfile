pipeline {

environment {

BUILD_SCRIPTS_GIT="https://github.com/ABhasgaran/JenkinsProject.git"

BUILD_SCRIPTS='mypipeline'

BUILD_HOME='/var/lib/jenkins/workspace'

}

agent any

stages {

stage('Checkout: Code') {

steps {

sh "mkdir -p $WORKSPACE/repo;\
git config --global user.email 'aaradhaa@googlemail.com';\
git config --global user.name 'alwar s';\
git config --global push.default simple;\
git clone $BUILD_SCRIPTS_GIT repo/$BUILD_SCRIPTS"

sh "chmod -R +x $WORKSPACE/repo/$BUILD_SCRIPTS"

}

}

stage('Yum: Updates') {

steps {

sh "sudo chmod +x $WORKSPACE/repo/$BUILD_SCRIPTS/scripts/update.sh"

sh "sudo $WORKSPACE/repo/$BUILD_SCRIPTS/scripts/update.sh"

}

}

}

post {

always {

cleanWs()

}

}

}