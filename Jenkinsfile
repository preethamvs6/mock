pipeline {
agent any

```
stages {

    stage('Clone') {
        steps {
            git branch: 'main',
                url: 'https://github.com/preethamvs6/mock.git'
        }
    }

    stage('Build') {
        steps {
            sh '''
            echo "Files in workspace:"
            ls -la
            '''
        }
    }

    stage('Deploy') {
        steps {
            sh '''
            sudo cp index.html /opt/tomcat/webapps/ROOT/index.html
            '''
        }
    }

    stage('Verify') {
        steps {
            sh '''
            ls -l /opt/tomcat/webapps/ROOT/index.html
            '''
        }
    }
}

post {
    success {
        echo 'HTML page deployed successfully to Tomcat'
    }

    failure {
        echo 'Pipeline failed'
    }
}
```

}
