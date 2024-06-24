pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('Limpando último pacote...') {

    }

    stage('Gerando versionamento...') {

    }
	
    stage('Criando novo pacote...') {

    }	
  
    stage('Checkout Repositório') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/erickamp/mba-clound-computing.git']]])
      }
    }

    stage('Direcionando para ambiente de testes...') {

    }	
	
    stage('Efetuando testes unitários...') {

    }
	
    stage('Direcionando para ambiente produção...') {

    }	
	
	
  }
}
