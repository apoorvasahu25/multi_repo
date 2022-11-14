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
                sh 'echo "multi-node-demo"'
                unstash(name: 'source')
                sh 'bash script.sh'
            }
        }
    }
}
