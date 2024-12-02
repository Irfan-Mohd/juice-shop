node {
    stage('Git SCM') {
        checkout scm
    }
    
    stage('Installing project dependencies and running a dependency scan using Snyk') {
        withCredentials([string(credentialsId: 'snyk', variable: 'SNYK_TOKEN')]) {
            sh "npm install"

            sh '''
                export SNYK_TOKEN=$SNYK_TOKEN
                snyk auth $SNYK_TOKEN > /dev/null 2>&1
                snyk monitor --org=e79d5c21-2f15-4823-90f1-0b34eef9773f
            '''
        }
    }

    stage('Source Code Analysis using SonarQube') {
       withCredentials([string(credentialsId: 'sonarqube', variable: 'envsonar')]) {
            def scannerHome = tool(name: 'SonarQube', type: 'hudson.plugins.sonar.SonarRunnerInstallation')
            withSonarQubeEnv('envsonar') {
                sh "${scannerHome}/bin/sonar-scanner"
            }
        }
    }
}
