pipeline {
  agent any
  stages {
    stage('Gitlab_checkout') {
      steps {
        sh '''node { dir(\'C:\\\\Git_DevOPS\') {
stage(\'Check-Out Git\') {
echo \'Prepare Data\'
     checkout([$class: \'GitSCM\', branches: [[name: \'*/master\']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: \'489be19e-a985-481d-a7e8-ebdea4e13ee8\', url: \'https://gitlab.com/aware-automate/myChannelDevOPS.git\']]])
}
}
parallel TestSonar_html:{
    stage(\'TestSonar_html\'){
        build \'TestSonar_html\'
    }
}
}'''
        }
      }
    }
  }