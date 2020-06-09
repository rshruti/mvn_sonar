
pipeline{
    agent any
    stages{
        stage('SCM-Checkout'){
            steps{
            git 'https://github.com/rshruti/mvn_sonar.git'
            }
        }
         	stage('Build Analysis') {
		steps {
			withSonarQubeEnv('sonar') {
				
				sh '/opt/maven/bin/mvn clean verify sonar:sonar -Dmaven.test.skip=true'
			}
		}
	}
	stage("Quality Gate") {
            steps {
              timeout(time: 2, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
              }

        }  
}

	stage ('Deploy') {
		steps {
			sh '/opt/maven/bin/mvn clean install -Dmaven.test.skip=true'
		}
	}

}}

