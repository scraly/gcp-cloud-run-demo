# gcp-cloud-run-demo

## Install and rin the Node.js app locally

npm install

npm start

## Build Docker image with Google Cloud Build

In Cloud Shell (for example):

```
$ export PROJECT=$(gcloud config list --format 'value(core.project)')
$ gcloud builds submit --tag gcr.io/$PROJECT/helloworld
````

### Deploy helloworld app to Cloud Run

In the GCP console, navigate to Cloud Run, and if needed, press Start Using Cloud Run.

Click CREATE SERVICE to create a new service and enter these sevice settings:

* Deployment platform	Cloud Run (fully managed)
* Region	us-central1 (Iowa)
* Service name	helloworld
* Authentication	Allow unauthenticated invocations

Click Next, then populate the Container image URL field by choosing your helloworld image.


Click on the CREATE blue button and give the service a moment to come up. When you get a URL, click it to test the service.

Deploy a new revision by clicking on the EDIT & DEPLOY NEW VERSION at the top of the page. Then under Advanced settings, got to the VARIABLES tab, and add the the following environmental variable:

Name	Value
TARGET	<scraly> (you're name)

Click on the DEPLOY blue button. When the new service revision finishes deploying and the new version starts receiving 100% of the traffic, re-test your application.