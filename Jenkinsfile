pipeline{
	   agent any
		    stages{
			   stage('SCM checkout')
				{
				git 'https://github.com/devopsyatin/maven'
				 }
		         }	 
				 stage ('Compile source code')
					{
						steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn Compile'
							}
				     		     }
								 
								}
					stage ('test source code')
					{
						steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn test'
							}
				     		     }
					}
					stage ('create package')
					{
						steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn package'
							}
				     		     }
					}
					stage ('install source code')
					{
						steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn install'
							}
				     		     }
					}
			}
		
	}
