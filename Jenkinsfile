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
                    // Execute the compiled C++ program and capture the output
                    def programOutput = sh(script: "./${SRN}-1", returnStdout: true).trim()
                    
                    // Print the output of the .cpp file
                    echo "Program Output: ${programOutput}"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application'
                // Add your deployment commands here if needed
                fewgvmbm
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

