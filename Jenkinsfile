import java.text.SimpleDateFormat


def sdf = new SimpleDateFormat("yyyy-MM-dd'T'HH:mm:ssX")
def publishAtDate = sdf.format(new Date())

pipeline {
  agent any
  parameters {
    string(
      name: 'PUBLISH_AT',
      defaultValue: publishAtDate,
      description: 'Default value is current date in the format yyyy-MM-dd\'T'|'HH:mm:ss',
      trim: true
    )
  }
  stages {
    stage (calling the argument)
      steps {
        sh 'echo "PUBLISH_AT:" +params.PUBLISH_AT'
      }
  }
}
