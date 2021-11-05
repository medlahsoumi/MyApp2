pipeline 
{
    agent any
    stages {
       stage ('Pull') {
            steps {
               script{
			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
			    userRemoteConfigs: [[
			    	credentialsId: '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',
				url: 'https://github.com/medlahsoumi/MyApp2.git']]])
               }
           }
       }
      stage('Build')
      {
      	    steps {
      	       script{
      	       sh "ansible-playbook ansible/build.yml"
      	       }
      	    } 
      }
}
}
