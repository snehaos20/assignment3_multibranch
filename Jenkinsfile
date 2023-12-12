pipeline{
    agent{
        label{
            label "slave1"
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
                sh "sudo chmod -R 777 /var/www/html"
               }
        }
        stage("deploying "){
            steps{
                dir('/var/www/html'){
                sh "sudo systemctl start httpd"
                sh "rm -rf *"
                sh "cp /mnt/branch2/assignment3_multibranch/index.html /var/www/html/"
                
                }
                
            }
        }
    }
}
