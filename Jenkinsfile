pipeline{
    agent{
        label{
            label "slave2"
            customWorkspace "/mnt/branch2"
        }
    }
    stages{
        stage("cloning git 23Q2 branch"){
            steps{
                sh "rm -rf *"
                sh "git clone https://github.com/snehaos20/assignment3_multibranch.git -b 23Q2"
                echo "cloning completed"
                 sh "sudo yum install httpd -y"
               }
        }
        stage("deploying "){
            steps{
                dir('/var/www/html'){
                sh "systemctl start httpd"
                sh "rm -rf *"
                sh "cp /mnt/branch2/assignment3_multibranch/index.html /var/www/html/"
                sh "chmod -R 777 /var/www/html"
                }
                
            }
        }
    }
}
