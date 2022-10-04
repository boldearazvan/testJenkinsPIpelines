pipeline {
    agent any 
    stages {
        stage('Hello') { 
            steps {
                echo "hello"
            }
        }
       stage('writeToFile') {
           steps {
               script {
                   def date = new Date()
                   def data = "Hello World\nSecond line\n" + date
                   writeFile(file: 'zorg.txt', text: data)
                   sh "ls -l"
               }
               archiveArtifacts artifacts: 'zorg.txt', followSymlinks: false, onlyIfSuccessful: true
           }
       }        
    }
}
