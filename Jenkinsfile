pipeline 
{
    agent{
		docker{
			image 'composer:composer'
		}
	}
	stages 
	{
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