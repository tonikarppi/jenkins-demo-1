pipeline {
  agent any
  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'the version of the application')
    booleanParam(name: 'executeTests', defaultValue: true, description: 'should tests be executed')
  }
  stages {
    stage("build") {
      steps {
        echo "Building the application..."
      }
    }
    stage("test") {
      when {
        expression {
          params.executeTests
        }
      }
      steps {
        echo "Testing the application..."
      }
    }
    stage("deploy") {
      steps {
        echo "Deploying the application..."
        echo "Deployed version ${params.VERSION}"
      }
    }
  }
}