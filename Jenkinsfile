#https://github.com/Saraja2607/SnowflakeBoT.git
#https://github.com/Vishnupriyar02/COP-SnowflakeBoT-Jenkins.git

def repo_name='SnowflakeBoT'
def snowsql_config="/home/ubuntu/.snowsql/config"


pipeline {
    agent any

    stages {
        stage('Checkout Git Branch') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Saraja2607/SnowflakeBoT.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/Saraja2607/SnowflakeBoT.git'
                sh 'python myFile.py'
                exec_sql=`snowsql --dbname ${database} --schemaname ${schema} --config '''+"${snowsql_config}"+''' --filename ${file} --connection srjreddy  2>&1`
            }
        }
        stage('Test') {
            steps {
                echo 'This job has been tested'
            }
        }
        stage('Deploy') {
            steps {
               echo 'This job has been tested'
            }
        }
    }
}
