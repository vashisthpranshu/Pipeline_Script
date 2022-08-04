pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Built-In Node"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Slave1') {
                    agent {
                        label "Slave1"
                    }
                    steps {
                        echo "Task1 on Agent/Slave1"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "Built-In Node"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
