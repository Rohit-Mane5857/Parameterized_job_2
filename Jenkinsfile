pipeline {
    agent any
    parameters {
        string(name: 'maven_version', defaultValue: '3.9.6', description: 'Pass the version of Maven')
        string(name: 'terraform_version', defaultValue: '1.8.5', description: 'Pass the version of Terraform')		
    }
    stages {
        stage('Download Maven') {
            steps {
                script {
                    def majorVersion = params.maven_version.tokenize('.')[0]
                    def mavenUrl = "https://dlcdn.apache.org/maven/maven-3/${majorVersion}/${params.maven_version}/binaries/apache-maven-${params.maven_version}-bin.tar.gz"
                    sh """
                    cd /var/lib/jenkins/
                    wget ${mavenUrl}
                    """
                }
            }
        }
        stage('Download Terraform') {
            steps {
                sh """
                cd /opt
                wget https://releases.hashicorp.com/terraform/${params.terraform_version}/terraform_${params.terraform_version}_linux_amd64.zip
                """
            }
        }		
    }
}
