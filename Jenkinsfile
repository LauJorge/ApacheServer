pipeline {
	agent any
	parameters {
    string(name: 'KeyName', description: 'Name of the ssh keys')
	string(name: 'PROJECT', description: 'Name of the project to be deployed')
	string(name: 'ENV', description: 'Name of the environment to be deployed')

   }
	stages {
		stage ('Submit Stack') {
			steps {
				sh "aws cloudformation create-stack --stack-name apache-server --template-body file://apache.yaml --region 'us-west-2' --parameters ParameterKey=KeyName,ParameterValue=${params.KeyName} ParameterKey=PROJECT,ParameterValue=${params.PROJECT} ParameterKey=ENV,ParameterValue=${params.ENV}"
			}
		}
	}
}
