node {
    stage('Prepare') {
        cleanWs()
        checkout scm          
    }     
    
    stage('Build container') {
        //download and unzip src code
        sh 'wget https://github.com/ariya/phantomjs/archive/2.1.3.zip; unzip 2.1.3.zip'
        //compile phantomjs
        sh 'cd phantomjs-2.1.3/; docker run -v $PWD:/src tubia/debian:wheezy /deploy/docker-build.sh'
    }
    
    stage('Run test') {
        //run yslow test
        sh 'phantomjs yslow.js -i grade -threshold "B" -f junit https://www.elastic2ls.com > yslow.xml'
    }
    
}
