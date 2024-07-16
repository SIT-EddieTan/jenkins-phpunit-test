pipeline 
{
    agent: any

    tools 
    {
        nodejs "nodejs"
        dockerTool 'docker'
    }

	stages 
	{
		stage('Initialize') 
        {
            steps 
            {
                script 
                {
                    // Set up Docker environment
                    def dockerHome = tool 'docker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
        }

		stage('Build') 
		{
			steps 
			{
				sh 'composer install '
			}
		}
		stage('Test') 
		{
			steps 
			{
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}