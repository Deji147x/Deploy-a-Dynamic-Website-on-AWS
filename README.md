![Alt text](Dynamic Web App.png)

# E-Commerce Web App Deployment on AWS

## Project Overview

This project involves the deployment of a dynamic e-commerce web application on AWS. The application is hosted on EC2 instances and utilizes various AWS services for high availability, fault tolerance, and scalability.

## Architecture

- **VPC Configuration**: Utilizes public and private subnets across two availability zones for improved reliability and security.
- **Internet Gateway**: Facilitates communication between the instances in the VPC and the Internet.
- **High Availability Setup**: Leverages two Availability Zones.
- **Security**: Employs Security Groups as a firewall.
- **Public Subnet Resources**: Includes a NAT Gateway, a Bastion Host, and an Application Load Balancer.
- **Private Subnet Resources**: Hosts web servers and database servers for enhanced security.
- **Database**: Utilizes MySQL RDS for database management.
- **Auto Scaling & Load Balancing**: Employs an Auto Scaling Group and an Application Load Balancer for traffic distribution and scalability.
- **Domain Name and DNS**: Managed using AWS Route 53.
- **Storage**: Uses AWS S3 for storing web files.
- **Permissions**: Implements IAM Roles for EC2 instances to access S3.
- **AMI Creation**: Involves creating an AMI from the configured EC2 instance.

## Deployment Scripts

### Software Installation Script

This script installs necessary software like Apache, PHP, MySQL, and additional utilities on the EC2 instance. It updates package repositories, installs server components, sets up PHP and MySQL, and configures server settings.

#### Key Commands:
- Update packages: `sudo yum update -y`
- Install Apache, PHP, MySQL: `sudo yum install httpd`, `sudo dnf install -y php ...`, `sudo dnf install -y mysql-community-server`
- Configure PHP and Apache settings.

### Application Installation and Configuration

This script deals with deploying the web application from an S3 bucket, configuring environment settings, setting permissions, and performing database migrations using Flyway.

#### Key Commands:
- Sync S3 bucket: `sudo aws s3 sync s3://[bucket-name] /var/www/html`
- Set permissions: `sudo chmod -R 777 /var/www/html`
- Configure application settings: `sudo sed -i ...` for various `.env` configurations.
- Flyway migration commands.

## Usage

- **Deployment**: Follow the scripts in order to set up the EC2 instances with the necessary software and application code.
- **Configuration**: Replace placeholders in the scripts with your specific AWS resource details and application configurations.
- **Migration**: Ensure the database is correctly set up before running Flyway migrations.

## Contributing

Contributions to this project are welcome. Please follow the standard fork-and-pull request workflow on GitHub.

## License

[Specify the license under which this project is released]
