@Library('My-Shared-Library') _

pipeline {
    agent { label 'slave' }

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        MAVEN_HOME = '/usr/share/maven'
        PATH = "${JAVA_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {  
                All.checkoutcode()
                }

            }
        }

        stage('Set up Java 17') {
            steps {
              script { 
              All.setupjava()
              }
            }
        }

        stage('Set up Maven') {
            steps {
                   script {
                   All.setupmvn()
                   }
            }
        }

        stage('Build with Maven') {
            steps {
                  script { 
                    All.buildproject() 
                  
                  }
            }
        }

        stage('Tag Build') {
            steps {
                script {
                    def buildTag = "build-${env.BUILD_NUMBER}"
                    tagBuild(buildTag, "Tagging build number ${env.BUILD_NUMBER}")
                }
            }
        }

    

        stage('Run Application') {
            steps {
                   script { 
                   
                   }
            }
        }

        stage('Validate App is Running') {
            steps {
                  script { 
                  
                  }
            }
        }

        stage('Clean Workspace') {
            steps {
                  script { 
                  
                  }
            }
        }

        stage('Gracefully Stop Spring Boot App') {
            steps {
                  script { 
                  
                  }
            }
        }
    }

    post {
        always {
            cleanup()
        }
    }
}
