pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'npm config set registry https://registry.npm.taobao.org'
                bat 'npm config get registry'
                bat 'npm install'
                bat 'npm run build:prod'
            }
        }
        stage('Deploy') {
            steps {
                bat 'xcopy .\\dist\\* D:\\views\\gsstest\\ /s/e/y'
            }
        }
    }
}
