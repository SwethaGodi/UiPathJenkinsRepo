pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'main', credentialsId: '89f4a99b-56af-48ad-be82-2c1f5110f75f', url: 'https://github.com/SwethaGodi/UiPathJenkinsRepo.git'
            }
        }
        stage('Build') {
            steps {
		echo "${WORKSPACE}"
                UiPathPack( outputPath: '${WORKSPACE}\\Output', projectJsonPath: '${WORKSPACE}', version: CurrentVersion())
            }
        }
    }
}




            
