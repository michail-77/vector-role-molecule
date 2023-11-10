pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git') {
            steps{
                git branch: 'main', credentialsId: 'a27000f3-c84f-4d79-8856-c4eba257a796', url: 'https://github.com/michail-77/vector-role-molecule.git'
            }
        }
        stage('Molecule install') {
            steps{
                sh 'pip3 install molecule==3.0.4'
#                sh 'pip3 install ansible-lint==5.1.3'
                sh 'pip3 install molecule_docker'
            }
        }
        stage('Molecule test'){
            steps{
                dir('roles/vector-role/') {
                    sh 'ls -l'
                    sh 'molecule test'
                    cleanWs()
                }
            }
        }
    }
}