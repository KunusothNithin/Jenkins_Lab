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
            mkdir -p out
            javac -d out *.java
        '''
    }
}

stage('Run Java') {
    steps {
        sh '''
            java -cp out Main
        '''
    }
}

    }

    post {
        success {
            echo "Build and run succeeded!"
        }
        failure {
            echo "Build or run failed."
        }
    }
}
