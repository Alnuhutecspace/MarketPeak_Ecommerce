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

**Step 4:** Deploying Updates to the Production Server

![Pull Request](./img/43.%20Pull%20Request.png) 


## Summary of the Project 

- Maintaining a secure and stable web server requires proper file permissions and ownership. In a typical Apache setup, all files within the `/var/www/html` directory should be owned by the Apache user to prevent permission issues. Setting directories to `755` ensures the owner has full control, while others can only read and execute. Files should be set to `644`, allowing read-write access for the owner and read-only for others. These permissions help safeguard the server from unauthorized modifications and preserve the integrity of the website content.

- Security best practices extend beyond file permissions. Keeping the system and Apache server up to date is vital, as outdated software can contain vulnerabilities. Regular updates should be performed using `yum update`, and automating this process with a weekly cron job helps ensure continuous protection without requiring manual intervention. When issues arise, common solutions include restarting Apache, correcting file ownership, adjusting `.git` folder permissions, or reviewing AWS security group settings to ensure HTTP traffic is allowed.

- For streamlined and consistent deployments, a CI/CD pipeline using GitHub Actions can be implemented. This setup allows code to be automatically deployed to an EC2 instance whenever changes are pushed to GitHub. By configuring a workflow that uses SSH to log in, pull the latest code, and reload Apache, the process becomes efficient and less prone to human error. This approach reduces manual deployment steps and supports faster iteration cycles.

- Several best practices contribute to a secure deployment pipeline. Using SSH keys instead of passwords enhances login security, while enabling HTTPS through Certbot ensures encrypted communication. A structured Git workflow—with version control, isolated branches, and automation—helps manage code changes effectively. Combined with tools like EC2 for hosting, Apache for web serving, GitHub for source control, and SSH for secure access, these practices form a robust and secure development environment.

- This hands-on project involved deploying an e-commerce platform using Git, Linux, and AWS EC2. The process began with initializing a Git repository, customizing a website template, and pushing it to GitHub using best practices like staging, committing, and branching. A main and development branch structure was followed to maintain organized and stable updates. However, challenges emerged during deployment when cloning the repository failed due to permission issues—first with HTTPS, then due to Git not being installed on the EC2 instance when attempting SSH cloning.

- Launching and configuring the EC2 instance involved several real-world troubleshooting tasks. Apache was installed to serve the website, but permission errors blocked access until correct file ownership and execution rights were assigned. Additionally, the security group was initially misconfigured, allowing only SSH (port 22) traffic, which blocked HTTP (port 80) access to the public. Once these issues were resolved—by adjusting security rules and configuring the web directory—the site was successfully deployed and accessible via the EC2 public IP. These experiences emphasized the importance of preparation, attention to detail, and problem-solving in cloud and DevOps workflows.
