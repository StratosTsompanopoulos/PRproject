# PRproject

Application link:
https://getstartednode-prp.mybluemix.net/

Basis application:
https://github.com/IBM-Cloud/get-started-node

## Installation / Configuration:
Based on: https://console.bluemix.net/docs/runtimes/nodejs/getting-started.html#getting-started

### Locally copy GIT:
- git clone https://github.com/IBM-Cloud/get-started-node
- cd get-started-node
- npm install
- npm start

### Install IBM CLoud CLI:
Based on the https://console.bluemix.net/docs/cli/index.html#overview
On get-start-node folder, Install & Verify
- curl -sL https://ibm.biz/idt-installer | bash
- ibmcloud dev help
Configure
-  ibmcloud login --sso

### Add named Space on IBM CLoud:
- Manage > Account > Cloud Foundry Orgs
- Add space named PRP on Dallas (other locations wont work)

### Work Locally to push the app to bluemix:
- ibmcloud login --sso
- ibmcloud target --cf (Select PRP)
- ibmcloud cf push

At this point the App is pushed and working on the IBM Cloud.
Check with:
- ibmcloud cf apps

### Add a database on IBM Cloud:
- Create resource > IBM Cloudant > Create connection (Use both legacy credentials and IAM.)

### Connect:
- navigate to the app > Create Connection > Connect to Cloudant (use the service ID created earlier from drop-down menu)
- click on restage when prompt
- check application on the provided link of the app

### Use database Localy:
- In the get-started-node directory, create a file called vcap-local.json with the content as indicated on the example
- go to the IBM Cloud dashboard and select your app > Connections. Click the IBM Cloudant menu icon (⋮) and select View credentials.
- Copy and paste just the url from the credentials to the url field of the vcap-local.json file, replacing CLOUDANT_DATABASE_URL.
- run localy (npm start). View your local app at http://localhost:3000
