# Getting started with App Engine


## Objectives

In this lab, you learn how to perform the following tasks:

- Initialize App Engine.

- Preview an App Engine application running locally in Cloud Shell.

- Deploy an App Engine application, so that others can reach it.

- Disable an App Engine application, when you no longer want it to be visible.


## **Initialize App Engine**

After activating cloud shell

> Initialize your App Engine app with your project and choose its region:

  `gcloud app create --project=$DEVSHELL_PROJECT_ID`

  - select a region for your app engine when prompted

> Clone the source code repository for a sample application in the hello_world directory:

  `git clone https://github.com/GoogleCloudPlatform/python-docs-samples`

> Navigate to the source directory:

  `cd python-docs-samples/appengine/standard_python3/hello_world`



## **Run Hello World application locally**


From the cloud shell

> Download and update the packages list

  `sudo apt-get update`

> Set up a virtual environment in which you will run your application:

  `sudo apt-get install virtualenv`

  - if prompted [Y/n], press Y and then Enter.

  `virtualenv -p python3 venv`

> Activate the virtual environment:

  `source venv/bin/activate`

> Navigate to your project directory and install dependencies:

  `pip install  -r requirements.txt`

> Run the application:

  `python main.py`

> Preview the application on by clicking on web preview

> To end the test, return to Cloud Shell and press `Ctrl+C` to abort the deployed service.




## **Deploy and run Hello World on App Engine**


> Navigate to the source directory:

  `cd ~/python-docs-samples/appengine/standard_python3/hello_world`

> Deploy your Hello World application.

  `gcloud app deploy`

  - if prompted, press Y and then Enter

  - This `app deploy` command uses the app.yaml file to identify project configuration

> Launch your browser to view the app

 `gcloud app browse`

 - This will lauch with the url http://YOUR_PROJECT_ID.appspot.com

 - copy and paste the url into a new browser window to view the result which should show

 #### End of Lab