pipeline {
    agent any
    tools {
        maven 'mavan3'
        jdk 'java17'
    }
    stages {
        stage('Download-Code-GIT') {
            steps {
                echo "download code from git"
                git branch: 'main', url: 'https://github.com/ChitreshChoudhary22/maven-jenkins4.git'
            }
        }
        stage('Build') {
            steps {
                echo "Build Java project using maven"
                sh 'mvn clean package'
            }
        }
        stage('Archive-Artifact') {
            steps {
                echo "Archiving the artifacts"
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
