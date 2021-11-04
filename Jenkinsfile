pipeline 
{
    agent any
    stages {
       stage ('Pull') {
            steps {
               script{
			checkout([$class: 'GitSCM', branches: [[name: '*/master']],
			    userRemoteConfigs: [[
			    	credentialsId: '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',
				url: 'https://github.com/medlahsoumi/MyApp2.git']]])
               }
           }
       }
}
}
