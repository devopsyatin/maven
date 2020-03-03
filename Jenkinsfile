pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/devopsyatin/maven.git'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven1') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven1') {
                    sh 'mvn test'
                }
            }
        }


        stage ('install Stage') {
            steps {
                withMaven(maven : 'Maven1') {
                    sh 'mvn install'
                }
            }
        }
        stage ('deploy to tomcat') {
            steps {
				sshagent(['656e7d80-ed1f-45c4-80a2-051f2968c4bc']) {
				sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@3.133.86.97:/var/lib/tomcat/webapps'
                                                                   }
            }
        }
         
}
}
