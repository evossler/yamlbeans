pipeline {
	agent any
	tools {
		maven 'Maven 3.3.9'
	}
	triggers { pollSCM('H */4 * * 0-6') }
	stages {
		stage('Build') {
			steps {
				checkout([$class: 'GitSCM', branches: scm.branches, doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/evossler/yamlbeans.git']]])
				sh 'mvn clean install'
			}
		}
	}
}
