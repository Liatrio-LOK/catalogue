node {
    stage('Build Image') {
        openshiftBuild (
            namespace: 'sock-shop', 
            bldCfg: 'catalogue-build', 
            checkForTriggeredDeployments: 'true', 
            showBuildLogs: 'true', 
            verbose: 'false'
        )
    }

    stage('Tag Image') {
        openshiftTag (
            sourceStream: 'catalogue',
            sourceTag: 'latest',
            destinationStream: 'catalogue',
            destinationTag: env.BRANCH_NAME,
            destinationNamespace: 'sock-shop'
        )
    }
}
