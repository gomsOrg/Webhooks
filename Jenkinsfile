prodName = ''

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                script {
                    echo server
                    if (server == "IBM") {
                        prodName = 'UCV'
                    } else {
                        prodName = 'Accelerate'
                    }
                    echo prodName
                    def inptext = readFile file: "test.js" 
                    inptext = inptext.replaceAll("PRODUCT", prodName)
                    def fileCount = readFile file: "test.js"
                    echo fileCount
                    if (fileCount.length() != 0) {
                        writeFile file: "test.js", text: ""
                    }
                    writeFile file: "test.js", text: inptext
                    def output = readFile file: "test.js"
                    echo output
                }
            }
        }
    }
}
