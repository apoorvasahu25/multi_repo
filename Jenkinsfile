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
            }
        }
    }
}
