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
                UiPathPack( outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'project.json', version: CurrentVersion())
            }
        }
        stage('Deploy') {
            steps {
                UiPathDeploy( credentials: Token(accountName: 'mirackhaqfin', credentialsId: 'e5716300-cb5e-456f-842d-db94f8c7e4ee'), environments: 'UiDemoEnvi', folderName: 'Default', orchestratorAddress: 'https://cloud.uipath.com/', orchestratorTenant: 'MiracleSoftwareSystemsDefault', packagePath: 'C:\\Users\\miracle\\AppData\\Local\\Jenkins\\.jenkins\\workspace\\UiPathPipeline_main\\Output')
            }
        }
    }
}
