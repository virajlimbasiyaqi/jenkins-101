pipeline {
    agent { 
        node {
            label 'devops_node'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {

        stage('ssh-agent'){
            steps{
                sshagent(['ssh-agent']){
                    sh'''
                    echo "git push master"
                    ssh -tt -o StrictHostKeyChecking=no viraj.limbasiya@122.1.5.8 ls
                    cd myapp
                    python3 hello.py
                    python3 hello.py --name=Brad
                    
                    '''
                }
            }
        }
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            // steps{
            //     sshagent(['ssh-agent']){
            //         sh'''
            //         ssh -tt -o StrictHostKeyChecking=no $remote_machine << "ENDSSH"
            //         cd myapp
            //         python myfile.py
            //         ENDSSH
            //         '''
            //     }
            // }
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
