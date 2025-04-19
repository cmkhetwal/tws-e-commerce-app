// if you get shared library not found error while running pipeline, then change the shared library in jenkins and in jenkinsfile

@Library("Shared") _
pipeline {
	
	agent { label "agent-vinod"}

	stages {

		stage("hello"){
			steps{
				script{
					hello()
				}
			}
		}
	 	stage("code"){
	 		steps{
	 			script{
	 				 	echo "this is cloning the code"
	 					clone("https://github.com/cmkhetwal/tws-e-commerce-app.git","master")
	 			}
	 		}

	 	}
	 	stage("build"){
	 		steps{
	 			script{
	 			docker_build("easy-shop","latest","cmkh")
	 			}
	 		}
	 	}
	 	stage("push"){
	 		steps{
	 			script{
	 			docker_push("easy-shop","latest","cmkh")
	 			}
	 		}
	 	}
	 	stage("deploy"){
	 		steps{
	 			script{
	 			compose()
	 			}
	 		}
	 	}
	}
}
