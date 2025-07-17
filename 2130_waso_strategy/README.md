# Project: E-Commerce Platform Deployment with Git, Linux and AWS 

## Complete Step by Step Guide on the Project 

### Stage 1: Implementing Version Control with Git 

1. Initialise Git Repository

- Change directory to my projects folder.

- Make a project directory for **MarketPeak_Ecommerce**. 

- Change directory into **MarketPeak_Ecommerce**. 

- Initialise Git repository. 

![Git Implentation](./img/01.%20Git%20Implementation.png)

2. Obtain and Prepare the E-Commerce Website Template 

- Template setup 

- Click on the recommended website template.

- Downloaded the template in zip folder. 

- Extracted the downloaded template into the project directory.

- A little text customisation was done to the template using VScode as editor. 

![Customising the Text](./img/02.%20Customising%20the%20Text.png) 

- Before stagging Git status was checked to verify what is to stage. 

3. Stage and Commit the Template Template to Git 

- The website template was added to Git repository 

- Git global configuration was setup for username and useremail 

- The changes were committed with a clear descriptive message. 

![Staging and Committing the Template](./img/03.%20Staging%20and%20Committing%20the%20Template.png) 

![Committing Cont](./img/04.%20Committing%20Cont.png) 

![Committing Cont.](./img/05.%20Committing%20Cont..png) 

![Linking Local to GitHub and Renaming Branch](./img/06.%20Linking%20Local%20to%20GitHub%20and%20Renaming%20Branch.png)

4. Push the code to Your GitHub Repository 

- Before pushing the repository from the local machine to remote repository the step is crucial for version control and collaboration 

- A remote repository was created named **MarketPeak_Ecommerce** without a README, .gitignore or license

![Creating Remote Repo](./img/07.%20Creating%20Remote%20Repo.png) 

![Creating Remote Repo Cont.](./img/08.%20Creating%20Remote%20Repo%20Cont..png) 

- The original branch was master and change to main using the command `git branch -M main` 

![Linking and Pushing Local Repo](./img/09.%20Linking%20and%20Pushing%20Local%20Repo.png) 

![Remote Repo After Push](./img/10.%20Remote%20Repo%20After%20Push.png) 

- A pull was carried out because of an update of the remote `README` file. 

![Git Pull to Update](./img/11.%20Git%20Pull%20to%20Update.png) 

### Stage 2: AWS Deployment 

To Deploy **"MarketPeak_Ecommerce"** platform we start by setting up Amazon EC2 instance: 

1. Set Up on AWS EC2 Instance

- Log on to the AWS management console 

![AWS Management Console](./img/12.%20AWS%20Management%20Console.png) 

- Launch an EC2 instance using an Amazon Linux AMI

![Launch EC2 Instance](./img/13.%20Launch%20of%20EC2%20Instance.png) 

![Naming EC2 Instance Cont.](./img/14.%20Naming%20EC2%20%20Instance.png)

- Choose Amazon Linux AMI 

![Choose EC2 Amazon Linux AMI](./img/15.%20Choose%20EC2%20Amazon%20Linux.png) 

- Enter name for new key pair and generate and download and download the key pair for access purpose. 

![Enter Name and Generate Key Pair](./img/16.%20Enter%20Name%20for%20Key%20Pair%20and%20Generate%20.png)

- Check the instance box (SSH), and click launch instance

![Connect to SSH](./img/17.%20Connect%20to%20SSH.png) 

- Instance launch successfully 

![Instance Success](./img/18.%20Instance%20Success.png) 

2. Clone the repository on the linux server. 

- Before deploying the ecommerce platform their is a need to clone GitHub repository to the AWS EC2 instance. 

- Connect to EC2 instance using the key pair of the instance generated. 

![Connect to EC2 Instance with the Key Pair](./img/19.%20Connect%20EC2%20Instance%20with%20the%20Key%20Pair.png) 

- Cloning the the repo to the ec2 server using https methods error was encounter.

![Cloning Using Https](./img/20.%20Cloning%20Using%20Https.png)  

- Cloning using ssh method alot steps was under gone since there was no ssh access on the repo. 

![Clone Using SSH](./img/21.%20Clone%20Using%20SSH.png) 

![Clone Using SSH Cont.](./img/22.%20Clone%20Using%20SSH%20Cont..png) 

![Clone Using SSH Cont.](./img/23.%20Clone%20Using%20SSH%20Cont..png) 

- Adding the ssh key to the GitHub remote before cloning using ssh key

![Clone Using SSH Cont.](./img/24.%20Clone%20Using%20SSH%20Cont..png) 

![Clone Using SSH Cont.](./img/25.%20Clone%20Using%20SSH%20Cont..png)

- Git Installation on the server

![Git Installation](./img/26.%20Git%20Installation.png)  

![Git Installation Cont](./img/27.%20Git%20Installation%20Cont.png) 

![Git Installation cont.](./img/28.%20Git%20Installation%20Cont..png)

![Git Clone](./img/29.%20Git%20Clone.png)

! [Git Clone Cont.](./img/30.%20Git%20Clone%20Cont..png) 

3. Installing a Web Server on EC2 

[Apache Http Sever (httpd)](httpd.apache.org) is widely usedweb server that serves HTML files and content over the internet. 

- Installing Apache  web server on the EC2 instance. Using this command `sudo yum install httpd -y` There is a need to update Linux server with the command `sudo yum update -y`

![Installing Apache](./img/31.%20Installing%20Apache.png) 

![Installing Apache Cont.](./img/32.%20Installing%20Apache%20Cont..png) 

![Installing Apache Cont.](./img/33.%20Installing%20Apache%20Cont..png) 

- Starting the server and ensures that it automatically starts on server for boot by enabling it.  

![Start the Web Server](./img/34.%20Start%20the%20Web%20Server.png)

![Enable and Check the Stats of Web server](./img/35.%20Enable%20and%20Check%20%20the%20Status%20of%20Web%20Server.png)

4. Configure httpd for Website

To serve the website from EC2 instance, configure **http** to point to the directory on the Linux server where the website code files are stored. Usually in /**var**/**www**/**html**, and also given permission to Apache and the file for execution.

- **Preparing the Web Directory:** Clear the default httpd web directory and copy MarketPeak_Ecommercewebsite files into it. 

- Apply the changes by reloading httpd service

![Prepare the Web Directory, Permission and Reload](./img/36.%20Prepare%20the%20Web%20Directory,%20Permission%20and%20Reload.png) 

5. Access Website from Browser 

- With **httpd** configured and website files in place, **MarketPeak_Ecommerce** platform is now live on the internet.

- Open a web browser and access the public IP of your EC2 instance to view the deployed website. `http://YOUR_EC2_IP/index.html` 

![Website Deployed](./img/37.%20Website%20Deployed.png) 

![Website Deployed Cont](./img/38.%20Website%20Deployed%20Cont.png) 

- To reach the website their is a need to check port 80 in the security group on the instance otr before launching the instance in the beginning. 

![Http Port](./img/39.%20Http%20Port.png)

### Stage #: Continuous Integration and Deployment 

To ensure smooth workflow for developing, testing and deploying the e-commerce platform, follow the structure approach. 

**Step 1:** Developing New Features and Fixes. 

- Create a Development Branch: Create a seperate branch. This isolates new features and bug fixes from the stable version of the website. 

![Development Branch](./img/40.%20Development%20Branch.png) 

- Implement Changes: On the development branch, add your new features or the bug fixes. It might include updating web pages, adding new products, or fixing known issues. 

**Step 2:** Version Control with Git 

- Stage Your Commit: After making the changes, add them to the stagging area in Git. 

- Commit Your Change: Securely save in the Git repository with a commit, with a proper descriptive message. 

![Stage and Commit](./img/41.%20Stage%20and%20Commit.png) 

- Push Your Changes to GitHub: Upload your development branch with the new chnages to GitHub. This enables collaboration and version tracking. 

![Git Push](./img/42.%20Git%20Push.png)

**Step 3:** Pull Request and Merging to the Main Branch 

- Create a Pull Request (PR): On GitHub, create a pull request to merge the development  branch into the main branch. 

- Review and Merge: Review the changes for any potential issues. Once satisfied merge the pull request into the main branch, incorporating the new changes.

- Push the Merged Changes to GitHub: Ensure that your local main branch, now containg the updates, is pushed to the remote repository on GitHub.

`git push origin main`

![Pull Request](./img/43.%20Pull%20Request.png) 

**Step 4:** Deploying Updates to the Production Server 

- Pull the Latest Changes on the Server: SSH into your AWS EC2 instance where the production website is hosted. Navigate to the website's directory and pull the latest changes from the main branch. 

`git pull origin main` 

- Restart the Web Server (If necessary): Depending on the nature of the updates to apply the changes.

`sudo systemctl reload httpd`

**Step 5:** Testing the New Changes

- Access the Website: Open a wen browser and navigate to the public IP address of the EC2 instance: Test the new features or fixes to ensure they workas expected in the live environment.

## Capstone Submission

- Maintaining a secure and functional web server involves setting correct file permissions and ownership. In Apache-based environments, files in `/var/www/html` should be owned by the Apache user, with directories set to `755` and files to `644`. These settings ensure the server operates smoothly while protecting content from unauthorized changes. Regular system updates using `yum update`, automated with cron jobs, help keep the operating system and Apache server secure with the latest patches. When issues occur, common fixes include restarting Apache, adjusting file ownership, modifying `.git` permissions, or correcting AWS security group settings to allow HTTP traffic.

- To streamline deployments and reduce human error, setting up a CI/CD pipeline with GitHub Actions is highly effective. This automation allows code to be deployed to an AWS EC2 instance each time a change is pushed to GitHub. The workflow typically uses SSH to log into the server, pull the latest code, and reload Apache. Using SSH keys instead of passwords, enabling HTTPS via Certbot, and following a structured Git workflow with isolated branches all contribute to a secure and efficient development process. Tools like GitHub, EC2, Apache, and SSH keys form the backbone of this deployment environment.

- The deployment project involved launching an EC2 instance with Amazon Linux, installing Apache, and deploying a customized e-commerce site from GitHub. Early challenges included repository cloning failures due to missing Git and permission issues with HTTPS and SSH. File ownership problems and misconfigured security groups (blocking HTTP access) further delayed deployment. Once these issues were resolved, the site became publicly accessible, offering valuable hands-on experience with server setup, security configurations, and DevOps workflows.
