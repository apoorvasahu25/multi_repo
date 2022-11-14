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
                sh 'echo "multi-node-demo my"'
                
                sh 'git clone https://github.com/apoorvasahu25/first.git'
                stash 'source'
            
                
                
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
                sh 'echo "multi-node-demo"'
                unstash 'source'
                sh 'bash script.sh'
            }
        }
    }
}
