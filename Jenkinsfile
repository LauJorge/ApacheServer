pipeline {
	agent any
	stages {
		stage ('Submit Stack') {
			steps {
				sh "aws cloudformation create-stack --stack-name apache-server --template-body file://apache.yaml --region 'us-west-2'"
			}
		}
	}
}
