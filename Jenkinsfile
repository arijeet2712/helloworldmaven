pipeline
{
    agent any
    stages
    {
        stage ('checkout STEP')
        {
            steps 
            {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '77f8d2d5-84cd-428d-9e4e-5230805aff19', url: 'https://github.com/arijeet2712/helloworldmaven']]])
            }
        }
        stage ('BUILD project')
        {
            steps 
            {
                tool name: 'localMaven', type: 'maven'
            }
        }
        
     post {
        success {
            mail bcc: '', body: 'build sUccedded', cc: '', from: '', replyTo: '', subject: 'build done', to: 'arijeet2712@gmail.com'
                }
          }
    }
}
