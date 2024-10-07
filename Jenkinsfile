node {
    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {
        withCredentials([string(credentialsId: 'b5d2f256-e810-4010-aebe-d5248f4cae88', variable: 'sonarenv')]) {
            sh '/home/jumpy-article/Downloads/sonarqube-10.7.0.96327/bin/linux-x86-64/sonar.sh -Dsonar.token=%sonarenv% -Dsonar.host.url=http://localhost:9000 -X'
        }
	}
}
