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
                catchError
                {
                    sh 'echo "multi-node-demo my"'
                    sh 'git clone https://github.com/apoorvasahu25/first.git'
                    stash(name: 'source')
                }
                   
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
