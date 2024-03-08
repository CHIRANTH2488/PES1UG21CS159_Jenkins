pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Run the build step with the build name 'PES1UG21CS159-1'.
                build 'PES1UG21CS159-1'
                // Compile the test.cpp file to produce an executable named 'output'.
                sh 'g++ test.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                // Execute the 'output' program for testing.
                // If the program fails, the 'sh' step will return a non-zero exit code, causing the pipeline to fail.
                sh './output' || error 'Test failed'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            // If any of the stages fail, print the message "Pipeline failed" to the console.
            echo 'Pipeline failed'
            // You can add additional actions here if needed.
        }
    }
}
