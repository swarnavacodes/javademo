pipeline {
    agent { 
        node {
            label 'docker-agent-java'
            }
      }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
        //         sh 'mkdir -p /home/jenkins/maven' 
        //                 sh '''
        //   mvn clean package
        // '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                // sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
            }
        }
    }
}
