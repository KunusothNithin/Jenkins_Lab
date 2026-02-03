pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/KunusothNithin/Jenkins_Lab.git'
            }
        }

        stage('Compile Java') {
            steps {
                sh '''
                    mkdir -p out
                    javac -d out *.java
                '''
            }
        }

        stage('Create JAR') {
            steps {
                sh '''
                    jar cf MyApp.jar -C out .
                    echo "JAR created successfully!"
                '''
            }
        }

        stage('Run JAR') {
            steps {
                sh '''
                    java -cp out Sample
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Build, JAR creation, and run succeeded!"
        }
        failure {
            echo "❌ Build or run failed."
        }
    }
}
