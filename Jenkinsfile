node {
    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {
        withCredentials([string(credentialsId: 'b5d2f256-e810-4010-aebe-d5248f4cae88', variable: 'sonarenv')]) {
		sh 'cd /home/jumpy-article/Downloads/sonar-scanner/bin/'
           	sh 'sonar-scanner -Dsonar.token=%sonarenv% -Dsonar.host.url=http://localhost:9000 -X'
        }
	}
}
