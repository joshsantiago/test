pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		checkout([
                    $class: 'GitSCM',
                    branches: [[name: "*/develop"]],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[
                        $class: 'SubmoduleOption', 
                        disableSubmodules: false, 
                        parentCredentials: true, 
                        recursiveSubmodules: true, 
                        reference: '', 
                        trackingSubmodules: false
                    ]], 
                    submoduleCfg: [],
                    userRemoteConfigs: [
                        [url: 'https://github.com/joshsantiago/test.git']
                    ]
                ])

                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
