pipeline {
    agent any

    parameters {
        string(name: 'USERNAME', defaultValue: 'admin', description: 'Enter your username')
    }

    stages {
        stage('Print Parameter') {
            steps {
                echo "You entered USERNAME = ${params.USERNAME}"
            }
        }
    }
}
