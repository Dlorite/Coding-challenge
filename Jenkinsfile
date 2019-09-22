.#!groovy
/**
        * Jenkins Pipeline for deploy a dummy web application
        * Author: David Lorite
 */
def gitJenkinsBranch = 'master'
def gitRepository =  'https://github.com/Dlorite/Coding-challenge.git'
def gitCredentialsID = "dlorite"

properties([
    parameters([
    ])
])

//Run it in any Linux node with kubectl and docker
node("linux&&kubcetl&&docker"){
    //First we download de 
    stage('Download repository') {
        checkout([$class: 'GitSCM', branches: [[name: "*/${gitJenkinsBranch}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: "${gitCredentialsID}", url: "${gitRepository}"]]])
    }
    //Run all test for the application
    stage('Run test'){
        echo "run some tests"
    }
    stage('Create docker image'){
        sh "docker build -t registry.tools.adidas-group.com/cmp/dummyWeb:test ."
    }
    stage{
        sh "docker push registry.tools.adidas-group.com/cmp/dummyWeb:test"
    }
    //Run the deployment with helm for dev-hzo as an example
    stage('Deploy it in dev'){
        sh "helm --kube-context=dev-hzo upgrade dummyWeb helm"
    }
}
