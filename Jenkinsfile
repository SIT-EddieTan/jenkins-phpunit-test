pipeline 
{
	agent 
	{
		docker 
		{
			image 'composer:latest'
		}
	}
	stages 
	{
		stage('Build') 
		{
			steps 
			{
				sh 'composer install'
			}
		}
		stage('Test') 
		{
			steps 
			{
                sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            }
		}
		
		stage('OWASP Dependency-Check Vulnerabilities')     
        {
            steps 
            {
                dependencyCheck additionalArguments: ''' 
                    -o './'
                    -s './'
                    -f 'ALL' 
                    --prettyPrint''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
        
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
        }

	}
	post
	{
		always
		{
			junit testResults: 'logs/unitreport.xml'
		}
	}
}
