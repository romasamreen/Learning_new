pipeline {
    agent any
    parameters{
        string(name:'person',defaultValue:'samreen',description:'admin user')
        booleanParam(name:'isMale',defaultValue:true,description:"Gender" )
        choice(name:'City',choices:['pune','delhi','jaipur','aurangabad'])
        
    }

    stages {
        stage('parameters') {
            steps {
                echo 'Hello World'
                sh 'echo "${person}"'
                sh '''
                    echo  "${isMale}"
                    echo  "${City}"
                    '''
            }
        }
        stage('continue? '){
            input{
                message 'should we continue'
                ok 'yes we should'
            }
            steps{
                echo 'Take userInput'
            }
        }
        stage('prod env'){
            steps{
                echo 'deployment in prod '
            }
        }
    }
    post{
        always{
            echo "hi will execute"
        }
        success{
            echo "execute whensucess"  
        }
        failure{
            echo "execute when fail"
        }
    }
}
