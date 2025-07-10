Project Deployment Documentation
Overview
This document outlines the steps taken to deploy the application and database infrastructure using AWS CloudFormation stacks, including network setup, server access, and application deployment.

Step 1: Collect Infrastructure Code
Collected CloudFormation template code from the AWS Management Console (browser).

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b2b8cc5d-215a-43a3-a1a2-f55bf7f5eddc" />

Configured the infrastructure components including:

Virtual Private Cloud (VPC)

Subnets (public and private)

Route Tables (to manage subnet routing)

Internet Gateway (to provide internet access to public subnets)

NAT Gateway (to allow private subnets outbound internet access)

Screenshot:
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/960355c8-a2fd-455d-92e6-24195f4abdbe" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/939c6a68-8ec0-404f-bd7f-565459ce39bf" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f1d2725c-24fe-4dd8-b825-94775f164938" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a05295a5-09b6-4666-a185-345794065785" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e1a78d44-3222-436f-b617-f3e66ffbea1f" />
<img width="1870" height="842" alt="Image" src="https://github.com/user-attachments/assets/e8278c12-ccaf-48d0-b7fb-a0cc867d1713" />
<img width="1771" height="953" alt="Image" src="https://github.com/user-attachments/assets/85a14dc4-4dd2-4d27-8005-f31bb0f7149d" />
<img width="1691" height="823" alt="Image" src="https://github.com/user-attachments/assets/cc4581c2-1c14-4797-8f52-b20028a3e074" />

Step 2: Deploy AWS CloudFormation Stacks
Created App and Database stacks using the collected CloudFormation templates.

Verified stack creation status and resources in the AWS Console.

Ensured networking components were properly attached and configured for communication between stacks.

Screenshot:
<img width="1846" height="862" alt="Image" src="https://github.com/user-attachments/assets/bce45429-53a5-4edc-9f62-0d66d919b4bd" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/fbbb10a3-b50c-44d9-8350-27b06e03a333" />

Step 3: Server Access Setup
Copy PEM File to Public Server
Copied the private key .pem file to the public server securely for SSH authentication.

This key is used to establish secure connections to both public and private servers.

Screenshot:
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/76ec9485-a278-4714-9e7f-f41884db5321" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ce4ed4e1-a811-412f-80a0-2483c5f2c5d9" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4639a86a-6731-4c71-a9ed-b9d40fc4b406" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ed6d761f-0da7-4afe-8966-92763cd70ba1" />

Connect to Servers
Used SSH from command prompt or terminal to connect to the public server.

From the public server, connected to the private server using the same key.

Example commands:

ssh -i mykey.pem ec2-user@public-server-ip
ssh -i mykey.pem ec2-user@private-server-ip
Screenshot:
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/794b2837-3f14-43ca-84c2-cfa21d19e2b0" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c5331dc9-0890-4e23-b083-def57f4d8314" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/23828386-0dc1-43ab-9b4b-2675d330fa32" />

Step 4: Application Deployment
Git Clone and Build
Cloned the application repository from GitHub onto the server.

bash
Copy
Edit
git clone https://github.com/your-repo/your-app.git
cd your-app
Built the application using the appropriate build commands.
 install
run build
Screenshot:
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d844a868-9b43-4456-857b-807e1212de0b" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ffa8c048-2d8d-47d7-8816-6c9d8da70189" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7a7f6a74-ec12-4594-b598-807b549788b1" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/74831fab-e52f-48b6-953d-b78fdc554892" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ee3fe096-4d59-4390-8ecc-d4748d06a4ed" />
<img width="1462" height="959" alt="Image" src="https://github.com/user-attachments/assets/fc11a76a-2b66-4afa-957d-3c5fa2d12d3b" />
<img width="1818" height="867" alt="Image" src="https://github.com/user-attachments/assets/bfb86e46-fd67-450a-83c6-a657635a41a1" />
<img width="1102" height="552" alt="Image" src="https://github.com/user-attachments/assets/1cf7becf-e5ae-41b5-9b8d-02667c34a13e" />
<img width="1496" height="962" alt="Image" src="https://github.com/user-attachments/assets/bb891aaf-2fe3-402b-a75d-385abef44a2a" />
<img width="1807" height="991" alt="Image" src="https://github.com/user-attachments/assets/3d62aa3e-43a1-4a8d-804f-4ad268be81ca" />
<img width="1884" height="937" alt="Image" src="https://github.com/user-attachments/assets/0eef0993-3512-4b2d-a42c-d07a9a69421c" />
<img width="1894" height="963" alt="Image" src="https://github.com/user-attachments/assets/8bee6e89-1e87-4844-b02e-6c6d7a1ed1ba" />
<img width="1829" height="972" alt="Image" src="https://github.com/user-attachments/assets/2c7948f0-7955-4a1b-b224-060f31359532" />
<img width="1892" height="988" alt="Image" src="https://github.com/user-attachments/assets/b3ab1e79-63df-4d63-9626-bfead4a51013" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a4377bd4-a2bd-46d2-b5a3-cdaa2a911bdb" />

Summary
Collected CloudFormation code via browser and configured network infrastructure.

Deployed App and Database stacks with subnets, route tables, internet gateway, and NAT gateway.

Configured server access using PEM keys and SSH.

Cloned and built the application from GitHub repository.
