#!/usr/bin/env groovy

node() {
    try {
        stage("Setup"){
            checkout scm
        }
        echo 'pepe'
        stage("Dependencies") {
            sh('npm install')
        }
        stage("Test") {
            nodejs(nodeJSInstallationName: 'node') {
                sh("npm run ci:test")
            }
        }
        stage("Build") {
            nodejs(nodeJSInstallationName: 'node') {
                sh("npm build")
            }
        }
    } catch(error) {
        throw error
    }  finally {
        cleanWs()
    }
}