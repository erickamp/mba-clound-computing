pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('Limpando último pacote') {
		steps {
				echo 'Escluir binários gerados anteriomente...'
		}  
    }

    stage('Gerando versionamento') {
		steps {
				echo 'Gerando versão para dos arquivos...'
		}  

    }
	
    stage('Criando novo pacote') {
		steps {
				echo 'Criando o novo pacote para liberação no ambiente de testes ...'
		}  

    }	
  
    stage('Checkout Repositório') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/erickamp/mba-clound-computing.git']]])
      }
    }

    stage('Direcionando para ambiente de testes') {
		steps {
				echo 'Substituindo ambiente anterior por este pacote...'
		}  

    }	
	
    stage('Efetuando testes unitários') {
		steps {
				echo 'Executando testes unitários para verificação de falhas...'
		}  

    }
	
    stage('Direcionando para ambiente produção') {
		steps {
				echo 'Substituindo ambiente de produção pelo novo pacote...'
		}
    }	

    stage('Verificando sistema de produção') {
		steps {
				echo 'Ambiente de produção atualizado e disponível para uso...'
		}
    }		
	
  }
}
