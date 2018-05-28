pipeline {
	agent any
	triggers { pollSCM('H */4 * * 0-6') }
	stages {
		stage('Build') {
			steps {
				checkout([$class: 'GitSCM', branches: [[name: '*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/evossler/snapfreeze.git']]])
				sh 'mvn clean install'
			}
		}
	}
}
