node {
    def app

    stage('Clone repository') {
      
        checkout scm
    }

    stage('test') {
        
        echo $(params.CHARTVER)
    }

/*    stage('Update GIT') {
            script {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    
                    //def encodedPassword = URLEncoder.encode("$GIT_PASSWORD",'UTF-8')
                    //sh "git switch master"
                    sh "cat ./charts/library/Chart.yaml"
                    sh "sed -i 'appVersion.*+appVersion: "${CHARTVER}"+g' Chart.yaml"
                    sh "cat ./charts/library/Chart.yaml"
                    sh "git add ."
                    sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.BUILD_NUMBER}'"
                    sh "git push -u origin main" 
    }
  }
}*/
}