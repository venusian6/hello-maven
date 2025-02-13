pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M398" and add it to the path.
        maven "M398"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
              //  git branch: 'main', url: 'https://github.com/venusian6/hello-maven.git' no need cuz we are using git directly
                // Run Maven on a Unix agent.
                sh 'mvn clean package -DskipTests=true'
                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }

        stage('Unit Test') {
            steps {
                // Run Maven tests
                sh "mvn test"
            }
        }
    }
}
