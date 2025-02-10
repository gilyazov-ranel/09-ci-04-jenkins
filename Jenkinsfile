pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/geerlingguy/ansible-role-ansible.git'
            }
        }
    

        stage('Run Molecule Test') {
            steps {
                sh '''
                    echo $PATH molecule test
                '''
            }
        }
    }

    post {
        success {
            echo 'Тесты Molecule прошли успешно!'
        }
        failure {
            echo 'Тесты Molecule завершились с ошибкой.'
        }
    }
}