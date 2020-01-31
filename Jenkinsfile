pipeline {
    agent any

    tools {
        maven 'maven-3.6.3'
        jdk 'jdk-8'
    }

    stages {
        stage('Build') {
            steps {
               sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('deploy') {
            steps {
               sh 'ansible-playbook -s playbook-openjdk.yml -k -u fiap --extra-vars "ansible_sudo_pass=fi@p2020"'
            }
        }
    }
}
