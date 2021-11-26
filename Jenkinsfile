pipeline {
    agent any
    stages {
        stage('first-level') {
                steps {
                        echo 'Hi, this is Harshhaa from C360'
			
                }
        }
	    stage('second-level'){
		    
		steps {
			input('Do you want to proceed?')
        }
	    }
        stage('third-level') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello"
                        }
        }
        stage('Four') {
                parallel {
                        stage('Unit Test') {
                                steps{
                                        echo "Running the unit test..."
                                }
                        }
                        stage('Integration test') {
                        agent {
                                docker {
                                        reuseNode false
					image 'ubuntu'
                                        }
			}
				steps {
					echo 'Running the integration test..'
				}
                               
			}  }
        }
    }
}
