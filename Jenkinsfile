pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sshagent(['41acdb23-f798-4c7c-86d1-3126b5f82bda']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@98.94.82.118 << 'EOF'

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
