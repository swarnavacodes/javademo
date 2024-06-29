pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
            }
      }
      stages {
    stage('Install Maven') {
      steps {
        // Use a shell script to install Maven based on your OS
        sh '''
          curl -sSL -o /tmp/apache-maven-38.6.0.tar.gz https://www.apache.org/dist/maven/3.8.6/binaries/apache-maven-38.6.0-bin.tar.gz
          tar -xzf /tmp/apache-maven-38.6.0.tar.gz -C /opt
          export PATH=/opt/apache-maven-38.6.0/bin:$PATH
        '''
      }
    }
      }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh 'mvn clean package'
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
