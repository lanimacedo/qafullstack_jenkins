pipeline {
    agent {
        docker {
            image "ruby:alpine"
        }
    }
    
    stages{
        stage("Build") {
            steps {
                sh "chmod +x build/alpine.sh"
                sh "./build/alpine.sh"
                sh "bundle install"
            }
        }
        stage("Testes") {
            steps {
                sh "bundle exec cucumber -p ci"
            }
        }
    }
}