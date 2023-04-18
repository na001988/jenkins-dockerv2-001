	agent any
	stages{
		stage("verify tooling"){
		 steps{
			sh '''
			docker version
			docker info
			docker-compose version
			'''
		 }
		}
		stage("Prune docker data"){
			steps{
			 //sh 'docker system prune -a --volumes -f'
			}
		}
		
		stage("Start container"){
			steps{
			 sh 'docker compose up -d --no-color --wait'
			 sh 'docker compose ps'
			}
		}
		stage("Run test"){
			steps{
			 sh 'docker run hello-world'
			}
		}
	}
	
	post{
		always{
		 //sh 'docker compose down --remove-orphans -v'
		 sh 'docker compose ps'
		}
	}
}
