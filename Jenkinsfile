pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sshagent(['34d9a865-ab04-47c9-b199-1a378442d7d6']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@54.82.22.211 << 'EOF'

                        echo "Connected to EC2"

                        cd /home/ubuntu

                        # Clone or pull repo
                        if [ -d "jenkis-ec2" ]; then
                            cd jenkis-ec2
                            git pull origin main
                        else
                            git clone https://github.com/kavyakr9599-dotcom/CICD-deployment.git
                            cd jenkis-ec2
                        fi

                        echo "Code updated successfully"

EOF
                    '''
                }
            }
        }
    }
}
