pipeline {
    agent {
        docker {
            image 'library/maven:3-alpine' 
            args '-v /root/.m2:/root/.m2'
   	    registryUrl 'https://hub.c.163.com' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}
