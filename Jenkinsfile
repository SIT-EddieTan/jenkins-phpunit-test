pipeline 
{
    agent any
	stages 
	{
		stage('Build') 
		{
			steps 
			{
				sh 'apt-get install -y composer'
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