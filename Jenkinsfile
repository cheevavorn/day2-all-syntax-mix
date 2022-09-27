pipeline {
    agent any
    
    environment {
        ENV_CHOICE = "${params.CHOICE}"
    }
    
    parameters {
        choice(name: 'CHOICE', choices: ['odd', 'even'], description: 'Pick something')
    }

    stages {
        stage("1st stage") {
            steps {
                script {
                    if (env.ENV_CHOICE == "odd") {
                        echo 'Any integer that cannot be divided exactly by 2 is an odd number.'
                    }else if(env.ENV_CHOICE == "even") {
                        echo 'Any integer that can be divided exactly by 2 is an even number.'
                    }
                }
            }
        }
        
        stage("2nd stage") {
            when {
                environment name: 'ENV_CHOICE', value: 'even'
            }
            
            steps {
                echo '2nd stage'
            }
        }
        
        stage("3rd stage") {
            when {
                environment name: 'ENV_CHOICE', value: 'odd'
            }
            
            steps {
                echo '3rd stage'
            }
        }
        
        stage("4th stage") {
            when {
                environment name: 'ENV_CHOICE', value: 'even'
            }
            
            steps {
                echo '4th stage'
            }
        }
        
        stage("5th stage") {
            when {
                environment name: 'ENV_CHOICE', value: 'odd'
            }
            
            steps {
                echo '5th stage'
            }
        }
    }
    
    post {
        always {
            echo 'END Job!'
        }
    }
    
}