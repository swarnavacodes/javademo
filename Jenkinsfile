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
                        sh '''
          curl -sSL -o /tmp/apache-maven-38.6.0.tar.gz https://downloads.apache.org/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz
          tar -xzf /tmp/apache-maven-38.6.0.tar.gz -C /opt
          export PATH=/opt/apache-maven-38.6.0/bin:$PATH
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
