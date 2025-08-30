pipeline
{
    agent any
    stages {
        stage('scm checkout')
        {steps {git 'https://github.com/ayodejiogunkanmi/mavenproject.git'}}

        stage('code compile')
        {steps {sh 'mvn compile'}}

        stage('unit test')
        {steps {sh 'mvn test'}}

        stage('code build')
        {steps {sh 'mvn package'}}

        stage('deploy to tomcat')
        {steps{ "sshagent(['cicd']) 
        { sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ubuntu@172.31.25.47:/opt/apache-tomcat-10.1.44/webapps"
}"}}

    }
}