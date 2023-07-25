import java.text.SimpleDateFormat
import java.util.TimeZone

def getCurrentDateTime() {
    def sdf = new SimpleDateFormat("yyyy-MM-dd'T'HH:mm:ssX")
    sdf.timeZone = TimeZone.getTimeZone("UTC")
    return sdf.format(new Date())
}

pipeline {
    agent any
    parameters {
        string(
            name: 'PUBLISH_AT',
            defaultValue: getCurrentDateTime(),
            description: 'Default value is the current date in the format yyyy-MM-dd\'T\'HH:mm:ss',
            trim: true
        )
    }
    stages {
        stage('Example Stage') {
            steps {
                sh '''
                    echo "PUBLISH_AT: ${PUBLISH_AT}"
                '''
            }
        }
    }
}
