# Static-web-deployment

This project demonstrates the deployment of a simple static website on a cloud platform, specifically AWS EC2. The website is served using the Apache web server running on an EC2 instance. The static site includes basic HTML, CSS, and JavaScript files.

## Project Overview
In this project, a static website containing personal information (name, email, and links) is deployed to an AWS EC2 instance. The Apache HTTP Server is used to serve the static content on port 80, and the site is publicly accessible via the EC2 instance's public IP address.

### Technologies Used
- Amazon Web Services (AWS): EC2 instance to host the website.
- Apache Web Server: Used to serve the static site on the EC2 instance.
- HTML/CSS/JavaScript: The frontend structure and design of the website.

### Steps for Deployment
1. Launch an EC2 Instance:
   
 - Select an appropriate instance (e.g., Amazon Linux or Ubuntu).
 - Configure security groups to allow HTTP traffic on port 80 and also allow ssh traffic in oerder to connect to your instance.

2. Install Apache Web Server:

  - Use the package manager to install Apache (httpd on Amazon Linux or apache2 on Ubuntu).
  - Start the Apache service and configure it to automatically start on boot.

3. Upload Static Files:

  - Copy the static website files (HTML, CSS, and JS) to the Apache document root (/var/www/html/).
  - Set appropriate permissions for Apache to serve these files.

4. Access the Website:

  - Use the EC2 instance's public IP address to access the site in a browser.

### Commands Used

- Install Apache: For Amazon Linux:

```
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
- For Ubuntu:

```
sudo apt update
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
```
- Upload Files: You can use SCP or SFTP to upload your static website files to the EC2 instance:

```
scp -i <key-pair-name>.pem <local-path-to-your-files> ec2-user@<public-ip>:/var/www/html/
```

- Set Permissions: For Amazon Linux:

```
sudo chown -R apache:apache /var/www/html/
```

- For Ubuntu:

```
sudo chown -R www-data:www-data /var/www/html/
```

- Restart Apache: Restart your web server for the changes to be saved:

```
sudo restart apache
```
- Restart: for Amazon linux:

```
sudo systemctl status httpd
```

- For Ubuntu

```
sudo systemctl status apache2
```
- view your site by using your <ip-address>

### Key Learnings

- EC2 Setup: How to configure and launch an AWS EC2 instance to host a website.
- Apache Configuration: How to install and configure Apache to serve static files.
- Website Hosting: Deploying a static website on a cloud platform using best practices.

## Conclusion
This project provides a foundational understanding of deploying a static website on a cloud platform, specifically AWS EC2, using Apache as the web server. By following the steps outlined, we successfully hosted a simple static website accessible through the EC2 instance's public IP address. This hands-on approach helped reinforce key concepts in cloud infrastructure management, server configuration, and basic website deployment. It also demonstrates the power of cloud platforms like AWS for quickly spinning up web-hosting environments that can scale as needed.



