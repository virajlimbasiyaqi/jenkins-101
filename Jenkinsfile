pipeline {
    agent { 
        node {
            label 'devops_node'
            }
      }
    stages {

        stage('Build') {
            steps {
                echo "test run"
                echo "Building.."
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
            }
        }
    }
}
