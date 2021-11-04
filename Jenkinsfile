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
