pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/devopsyatin/maven.git'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarpipeline') {
                    // Optionally use a Maven environment you':ve configured already
                    withMaven(maven:'Maven1') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}
