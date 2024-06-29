pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
            }
      }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh 'mkdir -p /home/jenkins/maven' 
                        sh '''
                  curl -sSL -o /tmp/apache-maven-38.8.tar.gz https://downloads.apache.org/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz
                  tar -xzf /tmp/apache-maven-38.8.tar.gz -C /home/jenkins/maven  # Replace with your desired directory
                  export PATH=/home/jenkins/maven/bin:$PATH
                  source /etc/profile  # Source shell profile (adjust path if needed)
          mvn clean package
        '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
            }
        }
    }
}
