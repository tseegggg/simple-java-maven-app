pipeline {
    environment {
        GOPATH = "$WORKSPACE/gopath/bin"
        PATH = "$GOPATH/bin:$PATH"
    }
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                bat 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
