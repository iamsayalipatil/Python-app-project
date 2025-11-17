# Deploy and Serve Your Python App with Nginx

## Introduction

This project offers a complete walkthrough for deploying a Python application in a production-ready environment using a proxy server. It covers everything from preparing both the development and server environments, installing essential packages, configuring the application, and setting up a proxy server like Nginx to handle and route incoming traffic effectively. Following this guide will help enhance the application's performance, scalability, and overall security.

## Prerequisites

Before you deploy this Python application, make sure the following tools and services are properly installed and set up:

1. Python 3.x – The app is built using Python version 3 or later.

2. Pip – Required to install and manage Python packages.

3. Git (optional) – Useful for cloning the project repository from a version control system.

4. Virtual Environment (venv) – Recommended to keep project dependencies isolated and manageable.

5. Proxy Server – Either Nginx or Apache is needed to route and manage incoming traffic to the application.


## Deployment Steps

### Step 1: Launch EC2 instance and Establishing a secure connection to your EC2 instance

  1. Launch instance

<p><img src="Images/launch instance.png" alt="Instance"></p>


  2. Copy ssh command

<p><img src="Images/copy ssh.png" alt="Instance"></p>


  3. Paste ssh command in Git bash terminal 

<p><img src="Images/bird.png" alt="Instance"></p>


### Step 2: Upgrade System Packages and Set Up Python

    1. update 
    #sudo yum update 

    2. install python 
    #sudo yum install python3 -y 

    3. install pip 
    #sudo yum install python3-pip

<p><img src="Images/update install python.png" alt="Instance"></p>



### Step 3: Upload/Clone Your Application

         Install a git

         #sudo yum install git -y



<p><img src="Images/install git.png" alt="Instance"></p>



2. Clone the Application and change into the pythonapp folder.

       clone git application 
       #git clone <git url> 

       Go inside the projrct folder
       #cd pythonapp 

<p><img src="Images/git clone cd ls.png" alt="Instance"></p>


### Step 4: Set up a virtual environment and activate it.

        create virtual environment 
        #sudo python3 -m venv myenv 

        activate file 
        #sudo source myenv/bin/activate


<p><img src="Images/myenv.png" alt="Instance"></p>



### Step 5: Install Dependencies.

         sudo pip install -r requirement.txt



<p><img src="Images/pip install.png" alt="Instance"></p>



### Step 6: Run the application in the background.

    sudo gunicorn --bind 0.0.0.0:5000 <file_name>:app -- daemon 



<p><img src="Images/gunicorn.png" alt="Instance"></p>    



### Step 7: Build the Proxy Server

1. Setting up Nginx as a Proxy Server

       sudo yum install nginx 



<p><img src="Images/install nginx.png" alt="Instance"></p>



2. Start, enable and check status of nginx
         
        sudo systemctl start nginx 
        sudo systemctl enable nginx 
        sudo systemctl status nginx  


<p><img src="Images/start nd enable nginx.png" alt="Instance"></p>



3. Set up a server block for your application

      1. open nginx.conf

       sudo vim nginx.conf 

<p><img src="Images/cd vim nginx.conf.png" alt="Instance"></p>


      2. Edit and add server block as show below 


<p><img src="Images/vim edit location.png" alt="Instance"></p>



### Step 8: Deployment Testing

   1. Copy Public IP

<p><img src="Images/copy pubilc ip.png" alt="Instance"></p>


   2. Final Output

<p><img src="Images/output.png" alt="Instance"></p>




## Summary

This project is a step-by-step guide to help you deploy a Python app using a proxy server. It shows you how to set up your environment, install what you need, configure the app, and use a proxy server like Nginx to handle requests smoothly.




