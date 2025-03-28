pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                powershell '''
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                powershell '''
                echo 'Test Step: We run testing tool like pytest here'

                cd ${env.LOCAL_DIR}

                # fill out the path to conda here
                .venv\\Scripts\\activate

                .venv\\Scripts\\python.exe --version

                # Complete the command to run pytest
                .venv\\Scripts\\python.exe -m pytest

                echo 'pytest runned'
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
