pipeline {
    agent any

    stages {
        stage('Deploy Docker container for packer') {
            steps {
                sh  (docker build -t packer .)'Building..'
                echo 'Building..'
            }
        }
        stage('Build Image') {
            steps {
                 sh (docker run -it packer <commands>)
                echo 'packaging'
            }
        }

    }
}
