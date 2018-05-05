# DeploymentPipeline
  The most basic continuous delivery pipeline will have, at minimum, three stages which should be defined in a Jenkinsfile: Build, Test, and Deploy. For this section we will focus primarily on the Deploy stage, but it should be noted that stable Build and Test stages are an important precursor to any deployment activity.


Stages as Deployment Environments

One common pattern is to extend the number of stages to capture additional deployment environments, like "staging" or "production", as shown in the following snippet.

stage('Deploy - Staging') {
    steps {
        sh './deploy staging'
        sh './run-smoke-tests'
    }
}
stage('Deploy - Production') {
    steps {
        sh './deploy production'
    }
}
