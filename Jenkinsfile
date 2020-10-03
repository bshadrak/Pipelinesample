pipeline {
    agent any
    stages {
        stage('Git-Checkout') {
            steps {
                    echo "CHecking out from git repo!!";
                    git 'https://github.com/bshadrak/Pipelinesample.git'
            }
        }
        stage('Build') {
            steps {
                    echo "building checkout project"
            }
        }
        stage('Unit') {
            steps {
                    echo "Junit passed successfuly!";
            }
        }
        stage('Quality') {
            steps{
                   echo "Sonargate quality gate passed success!";
            }
        }
        stage('Deploy') {
            steps {
                    echo "Deploying to stage env for more tests";
            }
        }
    }
    post {
        always  {
                  echo 'this runs always'
        }
        success {
                  echo 'runs only if success'
        }
        failure {
                  echo 'runs only if failed'
        }
        unstable {
                   echo 'runs only when job marked unstable'
        }
        changed {
                  echo 'runs if stateof pipeline has changed from previous'
        }
    }
}
