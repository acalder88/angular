#!/usr/bin/env groovy

node() {
    stage("Setup"){
        checkout scm
    }
    stage("Dependencies") {
        sh("npm install")
    }
    stage("Test") {
        sh("npm run ci:test")
    }
    stage("Build") {
        sh("npm build")
    }
}