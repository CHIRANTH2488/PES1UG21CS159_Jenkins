pipeline {
    // This line defines the agent where the pipeline will run. In this case, it will run on any available agent.
    agent any

    // This block defines the stages of the pipeline. A pipeline can have multiple stages, and each stage can have multiple steps.
    stages {

        stage('Build') {
            steps {
                build 'PES1UG21CS159-1'
                sh 'g++ test.cpp -o output'
            }
        }

        // This stage is named "Test". It has one step that executes the compiled program named 'output'.
        stage('Test') {
            steps {
                sh './output'
            }
        }

        // This stage is named "Deploy". It has one step that prints the message "deploy" to the console.
        stage('Deploy') {
            steps {
                echo 'deplo'
            }
        }
    }

    // This block defines the post-conditions of the pipeline. The post block will be executed after all the stages have finished.
    post {
        // This block defines what to do if the pipeline fails.
        failure {
            // This step will print the message "Pipeline failed" to the console if the pipeline fails.
            error 'Pipeline failed'
        }
    }
}
