Pipeline{
	   any agent{
		    Stages{
			   Stage('SCM checkout')
				{
				git 'https://github.com/devopsyatin/maven.git'
				 }
				 
				 Stage('Compile source code')
					{
						Steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn Compile'
							}
				     		     }
								 
								}
					Stage('test source code')
					{
						Steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn test'
							}
				     		     }
					}
					Stage('create package')
					{
						Steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn package'
							}
				     		     }
					}
					Stage('install source code')
					{
						Steps{
							withMaven(maven: 'Maven1')
							{
								sh 'mvn install'
							}
				     		     }
					}
			}
		}
	}
