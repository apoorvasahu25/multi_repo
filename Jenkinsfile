pipeline
{
    agent any
    stages 
    {
        stage('stage 1')
        {
           agent
            {
                label 'myvm'
            }
            steps 
            {
                sh'git init'
                sh'rm -rf first'
                sh'git clone https://github.com/apoorvasahu25/first.git'
                sh 'echo "multi-node-demo-1"'
                stash(name: 'source')           
            }
        }
        stage('stage 2') 
        {
            agent
            {
                label 'withother'
            }
            steps 
            {
                sh 'echo "multi-node-demo-2"'
                unstash(name: 'source')
                sh'cd'
                sh'cd /home/jenkins/jenkins-workspace/workspace/multi_repo@2/first/'
                sh 'chmod 777 script.sh'
                sh './script.sh'
            }
        }
    }
}
