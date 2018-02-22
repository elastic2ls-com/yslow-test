node {
    stage('Prepare') {
        cleanWs()
        checkout scm
        sh 'wget https://github.com/ariya/phantomjs/releases/download/2.1.3/phantomjs; chmod +x phantomjs'
            
    }     
    stage('Build') {

        sh './phantomjs yslow.js -i grade -threshold "B" -f junit https://www.elastic2ls.com > yslow.xml'
       }
}
