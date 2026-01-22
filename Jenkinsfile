pipeline {
    agent {
        docker {
            image 'node:18-alpine' // ใช้ Image นี้ที่มี Node.js มาให้แล้ว
            args '-u root:root'
            reuseNode true 
        }
    }
    stages {
        stage('Test npm') {
            steps {
                sh 'npm --version'
                sh 'node --version'
            }
        }
        stage('Build') {
            steps {
                sh 'rm -rf node_modules'
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}