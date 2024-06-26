# Lab 1
Tools and Software

This lab will walk you through the tools we will use in this class and the best practices for running the labs.

## ACE Hub Option
After connection to the CDN VPN, log into ACE Hub (https://hub.rangers.nhl.antcenter.net/environment). 

Set your ANT access secrets and load an environment with the class image (git.antcenter.net:4567/nyielding/acehub-tensorflow-image:latest)

If you do not have ACE Hub access yes, please use a Docker container on your personal machine for now, OR any other configuration management tool you wish for this lab (such as Anaconda). 


### Create Environment
Name:               Lab1_yourname (Lab1_tmachin)

Image:              git.antcenter.net:4567/nyielding/acehub-tensorflow-image:latest

Max CPUs Needed:    1

Required CPUs:      1

Memory:             8 Gi

GPU Type:           None

## Git Clone
Use the git clone command to pull this repository onto your virtual machine or running docker container in a folder of your choice.
I reccomend using a specified folder in your */remote_home/* directory

## Create a shell script
You will want to automate the setup process on the containerized machine you start up.  Create a shell script, `lab1Setup.sh` and have it do the following:

- update/upgrade the system
- install/upgrade pip
- pip install the python packages in the supplied requirements file (`python3 -m pip install -r requirements.txt`)

You can run this script by doing one of the following (you may need to make it executable, `chmod +x lab1Setup.sh`):

- `/bin/bash lab1Setup.sh`
- `./lab1Setup.sh`
 
## Python
Next we will write a python file called `lab1.py` that will run in the environment we just made.  In your cloned repo, create a new folder, `src`, then create `lab1.py` inside the folder.  The python file will do the following:

1. Make a list from one to ten and initialize to all ones
2. Make the first entry in the list a zero
3. Calculate the first 10 fibonacci numbers (starting with 0, 1) using a loop and put them in the previous list
4. Print the fibonacci numbers to the console

Make sure to provide comments in your code for each task so the instructor can clearly follow your process (aka showing work). 

# Make the lab easier to grade
In the interest of making the lab easier to grade, all labs from all students should be runable using the command `python3 (labfilename).py` in the terminal.  Always do a final check to ensure this works regardless of IDE.

When you use any data in your lab (usually provided by the instructor) do not modify the data as given by the instructor. Have your code expect all the data to be in `/opt/data` inside the VM (note this will require a `chmod a+w /opt/data` to ensure you can access the data without sudo). This way the code can run on any computer without modifying the data. You will need to make processed data in future labs so put all processed data in a folder with your name like `/opt/data/eeng645/lab1/yourname` or the project folder (but don't commit them to GitHub!) so your code does not fail because of data from other students. Thus, your code should run from a fresh empty data directory and make all necessary processed data and folders besides the given data for the lab.


## Git
For good programming practices and to make it easier to grade students will also push their code to the GitHub repository. 

To save space on our GitLab server never put large files in the git repository. Large files are around 100s of MB or larger. For example do not upload training data or models. Uploading figures is alright but please try not to make very large figures.

In order to ignore large files and other nuisance files we will add a file called `.gitignore` to the project root. We will add `*.pyc` and `.idea` to the `.gitignore` file which will ignore all `.pyc` files and the `.idea` folder which is PyCharm's project for your personal project settings. Always make the `.gitignore` before adding and committing files.

### Add and Commit Files
Use the GitHub Classroom assignment for each lab to submit your final code for each lab. Clone the template example with your name made automatically and modify the code for the lab (commit often!). In order to show that you can make new commits add a comment line to the python script with the text `new commit text`. Then add then commit that change and push that as well. This shows that you know enough to clone, add, commit, commit again, and then push a repo. 
