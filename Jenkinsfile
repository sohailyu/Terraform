pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("build") {
            step {
                echo 'building the application'
            }
        }
        stage("test") {
            when {
                expression {
                    params.executeTests
                }
            }
            step {
                echo 'testing the application'
            }
        }
        stage{"deploy"} {
            step {
                echo 'deploying the application'
                echo "deploying version ${params.VERSION}"
            }
        }

    }
}