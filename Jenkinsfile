#Inside script parameters block is asking for value for maven_version and terraform_version with some default value and description inside the stages downloading entered version of tool.
pipeline {
    agent any

    parameters {
        string(name: 'maven_version', defaultValue: '3.9.3', description: 'Pass the version of Maven')
        string(name: 'terraform_version', defaultValue: '1.8.5', description: 'Pass the version of Terraform')
    }

    stages {
        stage('Download Maven') {
            steps {
                sh 'cd /var/lib/jenkins/'
                sh 'sudo wget https://dlcdn.apache.org/maven/maven-3/${params.maven_version}/binaries/apache-maven-${params.maven_version}-bin.tar.gz'
            }
        }

        stage('Download Terraform') {
            steps {
                sh 'cd /opt'
                sh 'sudo wget https://releases.hashicorp.com/terraform/${params.terraform_version}/terraform_${params.terraform_version}_linux_amd64.zip'
            }
        }
    }
}