pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git url: 'https://github.com/KunusothNithin/Jenkins_Lab.git', branch: 'main'
            }
        }

        stage('Compile Java') {
            steps {
                sh '''
                    # Create output directory
                    mkdir -p out

                    # Compile all Java files in repo root
                    javac -d out *.java
                '''
            }
        }

        stage('Run Java') {
            steps {
                sh '''
                    # Run the main class (replace Sample with your main class name if different)
                    java -cp out Sample
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Build and run succeeded!"
        }
        failure {
            echo "❌ Build or run failed."
        }
    }
}
