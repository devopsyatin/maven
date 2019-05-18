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
        
         
}
}
