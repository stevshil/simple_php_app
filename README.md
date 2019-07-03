# Docker and OpenShift Assessment

## Requirement

As a team of 2 we want you to complete the following practical task, making full use of the DevOps tool set.  

You should also decide how you will break the task down to be able to complete it within the time scale.

In this task we want you to use the PHP and MySQL code verbatim (unchanged) to build 2 docker images;

* MySQL Database container which is populated on start up by the schema-data.sql script
  * The version of MySQL must be 5.7.19
  * The MySQL image has a special directory that if you place your SQL script in will load that on initial start
  * The database should map the /var/lib/mysql directory to a local directory called mydb for persistent data across recreation or updates of the database server
  * The database server must expose port 3306
  * The database servers host name must be **mysql** and the user must be **root** and the password also **root**
* PHP Apache server that will run the index.php program
  * You should use version 7.1 of PHP
  * The Web service should expose port 80
  * You will need to know where the DOCUMENT_ROOT is for the image you use and the DOCUMENT_INDEX should be index.php
  * Big hint, try using the **webdevops** images from Docker Hub

Make use of any already available Docker images from Docker Hub, creating the relevant Dockerfiles to include any necessary changes to the existing container.

# What you need to do

* Create the Dockerfiles to create the containers for the application, call the files;
    * Dockerfile.mysql
    * Dockerfile.app
* Create the docker-compose.yaml file to ensure that the 2 containers run, and that they are linked so that the app container sees the container called mysql
* Once you docker-compose.yaml works you should be able to point your web browser at your Linux host where the docker images are running and you should get a web form.  Type in UK and you will get 3 lines of data back;

```
#	First Name	Last Name	Email Address	  Age Location	Date
1	Steve	      Shilling	bob@builder.com	23	UK
2	Marcus	    Chinwag	  bob@builder.com	23	UK
3	Paul	      Filmer	  bob@builder.com	23	UK
```

Once you have the 2 containers running and the above output in your web browser, you should then convert your docker-compose.yaml to OpenShift YAML and launch your application in OpenShift.

You should also have a valid web URL of the form;
* **http://*2letterCountryCodeYourName1*.appsrvdev.conygre.com**
e.g.
* **http://cnsteveshilling1.appsrvdev.conygre.com**

**NOTE:** You must put your application on the appsrvdev.conygre.com server only.

# What about my code

All of your code must be in a shared BitBucket repository that you, your colleague and the instructors can review, and you should have a README.md file that tells me how to get your application running in OpenShift, which should include the oc commands that I need to run, and any builds or docker-compose commands to run, etc.

# Marking scheme

| Description | Score |
|-|-|
| Dockerfile content and names | 6 marks |
| Versions of the Docker images pinned | 2 marks |
| Mapping of persistent volume | 2 marks |
| Correct username and password for MySQL | 2 marks |
| Correct hostname for MySQL server | 2 marks |
| Correct final output from docker-compose | 4 marks |
| All your code in BitBucket with commits showing who worked on what | 6 marks |
| BitBucket URL has been provided to instructor | 4 marks |
| Actual working web application running in OpenShift | 4 marks |
| Information in the README.md file to tell us how to use your project and the OpenShift URL | 4 marks |
| **Total Marks** | **36 marks** |
