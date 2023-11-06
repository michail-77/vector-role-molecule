pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Get role') {
            steps {
                dir('vector-role') {
                    git branch: 'main', url: 'https://github.com/michail-77/vector-role.git'
                }
            }
        }
        stage('Molecule test') {
            steps {
                dir('vector-role') {
                sh 'molecule test'
                }
            }
        }
    }
}