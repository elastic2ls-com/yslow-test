node {
    stage('Prepare') {
        cleanWs()
        checkout scm
    }     
    stage('Build') {

        sh 'chmod +x phantomjs; ./phantomjs yslow.js -i grade -threshold "B" -f junit https://www.elastic2ls.com > yslow.xml'
       }
}
