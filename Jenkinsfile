pipeline {
    agent any

    tools {
        maven 'maven s/w'
    }

    stages{
        stage("Clone the Code"){
            steps{
                git credentialsId: 'git-creds', branch: 'main' url: 'https://github.com/Pratik543/netflix-java-deployment-automation.git'
            }
            post{
                success{
                    echo "========Code Cloned successfully========"
                }
                failure{
                    echo "========Code Cloning failed========"
                }
            }
        }
        stage('Maven Build') {
            steps {
                script {
                    def mavenHome = tool name: 'maven s/w', type: 'maven'
                    def mavenCMD = "${mavenHome}/bin/mvn"
                    // Run Maven build with parallel execution and skip tests if needed
                    sh "${mavenCMD} clean package -T 1C -DskipTests"
                }
            }
        }
        stage('Deployment Stage') {
            steps {
                script {
                    // Ensure target directory exists before copying
                    sh 'ls -l target'
                    // Deploy the WAR file to Tomcat
                    sh 'sudo cp target/NETFLIX-1.2.2.war /root/apache-tomcat-9.0.93/webapps'
                }
            }
        }
    }
    post{
        always{
            echo 'Cleaning up after build...'
            cleanWs() // Clean workspace after build
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}