pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sshagent(['55a91f5f-5e12-4872-a1eb-c558f0b22098']) {
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
