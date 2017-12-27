pipeline {
    agent any

    environment{
        PATH="/var/lib/jenkins/miniconda3/bin:$PATH"
    }

    stages {
        stage('Build environment') {
            steps {
                sh '''echo $PATH
                echo $SHELL
                conda info
                '''
            }
        }
        stage('Test environment') {
            steps {
                sh '''echo $SHELL
                        which pip
                        which python
                        conda info
                    '''
            }
        }
    }
    post {
        always {
            echo 'Finished'
            //bash 'conda remove --yes -n ${JOB_NAME} --all'
        }

    }
}
