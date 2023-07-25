import java.text.SimpleDateFormat
import java.util.TimeZone

def getCurrentDateTime() {
    def sdf = new SimpleDateFormat("yyyy-MM-dd'T'HH:mm:ssX")
    sdf.timeZone = TimeZone.getTimeZone("IST")
    return sdf.format(new Date())
}

pipeline {
    agent any
    stages {
        stage('Example Stage') {
            steps {
                script {
                    // Get the current date and time as the default value
                    def publishAtDate = getCurrentDateTime()

                    // Prompt the user for the value of the PUBLISH_AT parameter
                    def userInput = input(
                        id: 'userInput',
                        message: 'Enter Publish Date and Time:',
                        parameters: [string(defaultValue: publishAtDate, description: 'Publish Date and Time')]
                    )

                    // Use the provided value (userInput) for the PUBLISH_AT parameter
                    echo "PUBLISH_AT: ${userInput}"
                }
            }
        }
    }
}
