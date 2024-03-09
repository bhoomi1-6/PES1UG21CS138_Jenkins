pipeline {
    agent any

    environment {
        // Define environment variables if needed
        SRN = 'PES1UG21CS138'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the C++ program'
                script {
                    // Compile the .cpp file using a shell script
                    sh "g++ -o ${SRN}-1 myprogram.cpp"
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                script {
                    // Print the output of the .cpp file using a shell script
                    sh "./${SRN}-1 < input.txt > output.txt"
                    sh 'cat output.txt'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application'
                // Add your deployment commands here if needed
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
            // Add additional actions or notifications on failure
        }
    }
}

