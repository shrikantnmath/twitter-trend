pipeline {
    agent {
        node {
            label "maven"
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.4/bin:$PATH"
}
    stages {
        stage('CLEAN WORKSPACE') {
            steps {
                cleanWs()
            }
        }
        
        stage('GIT CHECKOUT') {
            steps {
                git branch: 'main', url: 'https://github.com/shrikantnmath/twitter-trend.git'
            }
        }

    }
}
