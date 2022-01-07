pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'build stage'
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/car.txt'
                sh 'echo "chassis" > build/car.txt'
                sh 'echo "engine" >> build/car.txt'
                sh 'echo "body" >> build/car.txt'
            }
        }
        
        stage('Test') {
            steps {
                echo 'test stage'
                sh 'test -f  build/car.txt'
                sh 'grep "chassis" build/car.txt'
            }
        }
        
        stage('Publish') {
            steps {
                echo 'publish stage'
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
