#!/usr/bin/env groovy

node() {
    try {
        stage("Setup"){
            checkout scm
        }
        echo 'pepe'
        stage("Dependencies") {
            nodejs(nodeJSInstallationName: 'node') {
                sh 'npm install'
            }
        }
        stage("Test") {
            sh("npm run ci:test")
        }
        stage("Build") {
            sh("npm build")
        }
    } catch(error) {
        throw error
    }  finally {
        cleanWs()
    }
}