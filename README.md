# InternshipWeekOne
Describes task completed in week one.

<h1>DAY ONE: </h1> 
  Launch Ec2 Instance:
    - Launched an Ec2 instance (Ubuntu) using a t2.micro free tier and storage of 8GB free tier with tag name "MyFirstEC2Instance".
    - The security group allows ssh and http connections on port 22 and 80 respectively.
    - Connection via an external terminal was established using a key pair downloaded at the process of creating the ec2 instance.
    - Scripts used for connection: 
        chmod 400 <name of downloaded key pair>
        ssh -i <name of downloaded key pair> <host username>@<host ip address>
    - Apache2 was installed using the below scripts:
        sudo apt update
        sudo apt install apache2 -y
        sudo systemctl start apache2
        sudo systemctl enable apache2
        echo "<h1>Hello from Ec2 instance </h1>" | sudo tee /var/wwww/html/index.html 
        <img width="903" alt="Screenshot 2025-01-23 at 19 02 28" src="https://github.com/user-attachments/assets/c7c35935-77bf-48a6-ad9b-ff9a74c0d0eb" />



<h1>DAY TWO: </h1>  
  Managing Instance: 
    - The first stage comprised of stopping, starting and terminating an instance
    - The second phase is to launch an ec2 instance and create an AMI from the instance and launch a new instance from the AMI
    ALL CONFIRGURATIONS FROM INITIAL INSTANCE REMAIN SAME AS NEWLY CREATED INSTANCE.
    <img width="1680" alt="Screenshot 2025-01-27 at 12 10 13" src="https://github.com/user-attachments/assets/14a1bc18-5844-446a-ae3a-e7fde9fa72ab" />


<h1>DAY THREE: </h1> 
  DEPLOY A WORDPRESS APPLICATION USING AWS LIGHTSAIL:
    - A ubuntu instance was created in aws lightsail as its OS using wordpress as the blueprint
      <img width="1680" alt="Screenshot 2025-01-29 at 10 38 48" src="https://github.com/user-attachments/assets/23f64791-b0fa-4aeb-ab5b-2d088dc1d829" />
    - Connection was established via lightsail browser-based ssh but access to the wordpress dashboard was via the public ip

<h1>DAY FOUR: </h1> 
  ELASTIC IP ALLOCATION:
    - This task involves two steps:
      - 1. Create an elastic IP and associate the ip to an ec2 instance
           Access the ec2 instance via a web browser with the newly assigned IP
      - 2. Modify security group to allow https connection on port 443
            Test connection via https.
        <img width="1680" alt="Screenshot 2025-01-29 at 11 12 18" src="https://github.com/user-attachments/assets/5ef7cc19-5d3f-4c35-95ba-855e6055081e" />

<h1>DAY FIVE: </h1> 
  Task One: 
    - Launched an ec2 instance and installed nginx and hosted a custom html page using the following commands:
        sudo apt update
        sudo apt install nginx -y 
        sudo systemctl start nginx
        sudo systemctl enable nginx
        echo "<h1>Hello from NGINX on EC2 instance </h1>" | sudo tee /var/http/www/html/index.html

 Task TWO:
   - Launched a light sail instance and deployed a simple node.js app:
      Steps followed:
       - Created a node.js server with the commands:
           - Installed nodejs unto my local computer and checked the version: node -v
           - npm init -y
           - npm install express
           - Scripts:
              <p><i> const http = requiree('http)<br>
               const server = http.createServer((req, res) => { <br>
                 res.end('Hello from Node.js on LightSail!'); <br>
               });<br>
               server.listen(80, () => console.log('Server running on port 80')); </i></p>
      - A github repo was initiated to push the code to github:
      - github link: https://github.com/ngodson/ngodson-AWSLightSailNodeJS.git
    
      - In the aws lightsail nodejs blueprint, i navigated to the folder called htpDocs and deleted all files using:
      -   rm -rf *
      -   and cloned my github repository into this folder: git clone <github repo link>
      -   The node.js page was established on instance ip:port number
      
  Task Three: 
    - Creating an AMI from ec2 instance an launch new instance from it. Veryfy the new instance has the same configuration.
    - steps are similar to day two.

  
<h1>DAY SIX: </h1>
    Review and document:
      - Documentation on week one can be found in: https://github.com/ngodson/InternshipWeekOne/edit/main/README.md

