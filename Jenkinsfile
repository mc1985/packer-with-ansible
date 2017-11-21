pipeline {
    agent any
    stages {
        stage('GIT Pull ansible playbook') {
            steps {
                git(
                     url: 'https://github.com/mc1985/ansible-configuration.git'
                     branch: '${branch}'
                  )
            }
        }
        stage('Deploy Docker container for packer') {
            steps {
                sh "docker build -t packer .)"
                echo 'Building..'
            }
        }
        stage('Build Image') {
            steps {
                 sh "docker run -it packer <commands>)"
                echo 'packaging'
            }
        }

    }
}
