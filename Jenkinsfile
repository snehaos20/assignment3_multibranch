pipeline{
    agent{
        label{
            label "slave1"
            customWorkspace "/mnt/branch1"
        }
    }
    stages{
        stage("cloning git 23Q1 branch"){
            steps{
                sh "rm -rf *"
                sh "git clone https://github.com/snehaos20/assignment3_multibranch.git -b 23Q1"
                echo "cloning completed"
                sh "chmod -R 777 /mnt"
            }
        }
        stage("deploying "){
            steps{
                dir('/var/www/html'){
                    sh "yum install httpd -y"
                    sh "systemctl start httpd"
                    sh "rm -rf *"
                    sh "cp /mnt/branch1/assignment3_multibranch/index.html /var/www/html/"
                    sh "chmod -R 777 /var/www/html"
                }
                
            }
        }
    }
}
