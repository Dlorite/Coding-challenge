#!groovy
/**
        * Jenkins Pipeline for deploy a dummy web application
        * Author: David Lorite
 */
def gitJenkinsBranch = 'master'
def gitRepository =  'https://github.com/Dlorite/Coding-challenge.git'

properties([
    parameters([
    ])
])

node{
    stage('Download repository') {
        checkout([$class: 'GitSCM', branches: [[name: "*/${gitJenkinsBranch}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: "${gitCredentialsID}", url: "${gitRepository}"]]])
    }
}
