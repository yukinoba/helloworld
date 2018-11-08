#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'source ~/.bashrc'
	sh 'export PATH=/usr/local/bin/npm:/usr/local/bin/node:$PATH'
	sh 'npm config set registry http://registry.npmjs.org/'
        sh 'npm install'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha --timeout 10000 --exit'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
