node {
    def app

    stage('Clone repository') {
      
        checkout scm
    }

    stage('test') {
        
        echo CHARTVER
    }

    stage('Update GIT') {
        
        sh "cat ./charts/library/Chart.yaml"
        sh "sed 's/appVersion:*/appVersion: ${CHARTVER}/g' ./charts/library/Chart.yaml"
        sh "cat ./charts/library/Chart.yaml"
    /*    sh "git add ."
        sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.BUILD_NUMBER}'"
        sh "git push -u origin main" 
    */        
        
    }
}