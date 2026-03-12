pipeline{
	agent none
	stages{
		stage ('Build'){
			agent{ label 'master' }
			steps{
				sh 'echo " Build running on master"'
			}
		}
		stage ('Deploy'){
			agent{ label 'node1' }
			steps{
				sh 'echo " Deploy running on node1"'
				sh " echo trying the webhook "
			}
		}	
	}
}
