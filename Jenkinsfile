pipeline 
{
    agent any
    stages {
       stage ('Pull') {
            steps {
               script{
			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
			    userRemoteConfigs: [[
			    	credentialsId: 'g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',
				url: 'https://github.com/medlahsoumi/MyApp2.git']]])
               }
           }
       }
       
      stage('Install')
      {
      	    steps {
      	       script{
      	       sh "sudo npm install"
      	       }
      	    } 
      }  
           
      stage('Build')
      {
      	    steps {
      	       script{
      	       sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
      	       }
      	    } 
      }
      stage('Docker')
      {
      	    steps {
      	       script{
      	       sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
      	       }
      	    } 
      }
}
}
