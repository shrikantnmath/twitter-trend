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

stage("BUILD"){
            steps {
                 echo "----------- build started ----------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                 echo "----------- build complted ----------"
            }
        }

stage("UNIT TEST"){
            steps{
                echo "----------- unit test started ----------"
                sh 'mvn surefire-report:report'
                 echo "----------- unit test Complted ----------"
            }
        }
    
	}
	
}
