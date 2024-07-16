pipeline 
{
    agent any
	stages 
	{
		stage('Build') 
		{
			steps 
			{
				sh 'install composer -y'
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