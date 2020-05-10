pipeline {
    agent any
    stages {
        stage('Git-Checkout') {
            steps {
                echo 'Checking Git Info!!';
                git 'https://github.com/vindee999/Pipeline_Script.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Build passed Successfully!!';
                bat label: '', script: 'Build.bat'
            }
        }
        stage('Quality-Gate') {
            steps {
                echo 'Quality-Gate passed Successfully!!';
                bat label: '', script: 'Quality.bat'
            }
        }
        stage('Unit-Test') {
            steps {
                echo 'Unit-Test passed Successfully!!';
                bat label: '', script: 'Unit1.bat'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Pass!!';
                bat label: '', script: 'Deploy.bat'
            }
        }
    }
    post { 
        always { 
            echo 'I will always run!'
        }
        success { 
            echo 'I will run if success!'
        }
        failure { 
            echo 'I will run if failed!'
        }
        unstable { 
            echo 'I will run only if run was marked as unstable!'
        }
        changed { 
            echo 'I will run if state of pipeline is changed!'
        }
    }
}
