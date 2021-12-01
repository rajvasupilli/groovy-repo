node('master') {
    checkout scm: ([
                    $class: 'GitSCM',
                    userRemoteConfigs: [[credentialsId: 'raju_github',url: 'https://github.com/rajvasupilli/groovy-repo.git']],
                    branches: [[name: 'refs/remotes/origin/main']]
            ])
    
    def version = "version_r4.3"
    
    //idvUiConfiguration = readYaml file: "${env.WORKSPACE}/settings.yml"
    idvUiConfiguration = readYaml file: "${env.WORKSPACE}/deployment_version.yml"
    currentPlatformSettings = idvUiConfiguration.buildversion.version_r4_1.idvui_image_version
    currentPlatformSetting = idvUiConfiguration.buildversion."$version".idvui_image_version
    println "$currentPlatformSettings"
    println "$currentPlatformSetting"
    }
    
pipeline {
  agent none
   stages {  
    stage('Build') {
     steps {
        // Run the maven build
        println "Build Stage Executed!!!"
     }
    }
    stage('Results') {
        steps {
        println "Results Stage Executed!!!"
        }
    }
   }
}

