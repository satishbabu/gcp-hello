# Deploying a simple Java App onto GCP

Here are the steps:
1. Create a springboot app with url /hello to say 'Hello GCP'
1. Create a google project from google cloud console
1. Configure the google cloud shell local installation 'gcloud config set project <new-google-project-id>'
1. Add following to maven pom.xml in plugin section


    <plugin>
        <groupId>com.google.appengine</groupId>
        <artifactId>appengine-maven-plugin</artifactId>
        <version>1.9.86</version>
        <configuration>
            <deploy.projectId><new-google-project-id></deploy.projectId>
            <deploy.version>1</deploy.version>
        </configuration>
    </plugin>

5. Create app.yaml under src/main/appengine with following


    runtime: java11
    instance_class: F1

6. Deploy to google app engine using 'mvn appengine:deploy'
1. Launch a browser wth url 'gcloud app browse'
1. Stream logs using 'gcloud app logs tail -s default'


   
