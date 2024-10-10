node {
    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {
        withCredentials([string(credentialsId: 'b5d2f256-e810-4010-aebe-d5248f4cae88', variable: 'sonarenv')]) {
		//sh 'cd /home/jumpy-article/Downloads/sonar-scanner/bin/'
           	sh '/opt/sonar-scanner/bin/sonar-scanner -Dsonar.token=sqp_e3f0eb6df6249cf99571372b3a936c70216d73d9 -Dsonar.host.url=http://localhost:9000 -X'
        }
	}
}
