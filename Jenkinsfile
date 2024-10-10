node {
    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {
        withCredentials([string(credentialsId: 'sonarqubeauth', variable: 'sonarenv')]) {
		//sh 'cd /home/jumpy-article/Downloads/sonar-scanner/bin/'
           	sh '/opt/sonar-scanner/bin/sonar-scanner -Dsonar.token=%sonarenv% -Dsonar.host.url=http://localhost:9000 -X'
        }
	}
}
