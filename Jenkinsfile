pipeline{
    agent{
        label{
            label "slave-2"
            customWorkspace "/mnt/branch3"
        }
    }
    stages{
        stage("cloning git 23Q3 branch"){
            steps{
                sh "rm -rf *"
                sh "git clone https://github.com/snehaos20/assignment3_multibranch.git -b 23Q3"
                echo "cloning completed"
            }
        }
        stage("deploying "){
            steps{
                sh "chmod -R 777 /var/www/html/"
            sh "cp /mnt/branch3/assignment3_multibranch/index.html /var/www/html/"
                
                
            }
        }
    }
}
