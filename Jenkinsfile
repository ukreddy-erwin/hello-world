pipeline {
  agent any
  stages {
    stage('github clone') {
      steps {
        echo 'cloning repo'
        git(url: 'git@github.com:uday-globuslive/hello-world.git', branch: 'master', credentialsId: 'github-user', poll: true)
      }
    }

    stage('maven build') {
      steps {
        dir(path: 'webapp') {
          sh '''$MAVEN_HOME/bin/mvn clean package
pwd'''
        }

        echo 'build stage done'
      }
    }

  }
}