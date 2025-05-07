pipeline {
    agent any

    environment {
        // Set environment variables (optional but clean)
        WAR_NAME = "my-webapp2.war"
        DEPLOY_DIR = "D:\\DevopsTaining\\GitTasks\\my-webapp2" // e.g., /opt/tomcat/webapps
    }

    tools {
        maven 'MAVEN_HOME'   // Ensure this is configured in Jenkins Global Tool Configuration
        jdk 'JAVA_HOME'      // Ensure JDK is configured as well
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Narasimha191031018/DeployWebapp2'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                // Adjust path if deploying locally, or use SCP if deploying to a remote server
                sh """
                cp target/${my-webapp2} ${"D:\DevopsTaining\All softwares\apache-tomcat-9.0.104\apache-tomcat-9.0.104"}
                echo "Deployment done!"
                """
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
