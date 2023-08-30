pipeline {
  agent any
  stages {
    stage("Build") {
      steps {
        git url: 'https://github.com/saurabhrawat2606/hello-world.git'
        withMaven {
          sh "mvn clean verify"
        } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
      }
    
    }
  stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = "mydockerimage:latest"
                    def dockerFile = "Dockerfile" // Make sure your Dockerfile is in the root directory of your project
                    def dockerBuildCmd = "docker build -t ${dockerImage} -f ${dockerFile} ."
                    sh dockerBuildCmd
                                   
                    }
                            }
  }
    
}
}

  
