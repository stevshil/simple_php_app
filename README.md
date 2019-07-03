# Docker and OpenShift assessment

In this task we want you to use the PHP and MySQL code verbatim to build 2 docker containers;

* MySQL Database container which is populated on start up by the schema-data.sql script
  * The version of MySQL must be 5.7.19
  * The MySQL image has a special directory that if you place your SQL script in will load that on initial start
  * The database should map the /var/lib/mysql directory to a local directory call mydb for persistent data across recreation of the database server
  * The database server must expose port 3306
  * The database servers host name must be **mysql** and the user must be **root** and the password also **root**
* PHP Apache server that will run the index.php program
  * You should use version 7.1 of PHP
  * The Web service should expose port 80
  * You will need to know where the DOCUMENT_ROOT is for the image you use and the DOCUMENT_INDEX should be index.php
  * Big hint, try using the **webdevops** images from Docker Hub

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
*2letterCountryCodeYourName1.appsrvdev.conygre.com*

You must only put your application on the appsrvdev.conygre.com server.

# What about my code

All of your code must be in BitBucket repository that the instructors can review, and you should have a README.md file that tells me how to get your application running in OpenShift, which should include the oc commands that I need to run, and any builds or docker-compose commands to run, etc.
