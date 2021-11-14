pipeline {
  agent any
  stages {
    stage('Code Connect') {
      steps {
        git(url: 'https://github.com/pavansw/simpleMavenJunit.git', branch: 'master', changelog: true, poll: true)
        echo 'This is Stage for SCM'
      }
    }

    stage('Clean') {
      steps {
        sh 'mvn clean'
        echo 'Code clean'
      }
    }
    
    stage('Compile') {
      steps {
        sh 'mvn compile'
        echo 'Code compile'
      }
    }

    stage('Testing') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Packaging') {
      steps {
        sh 'mvn package'
      }
    }

    stage('TEST RUN') {
      steps {
        sh 'java -jar target/gs-maven-0.1.0.jar'
      }
    }

  }
}
