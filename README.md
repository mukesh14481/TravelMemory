# TravelMemory


Task 1

Login to AWS
AWS Console → EC2 → Launch Instance named as : backend-server-1
EC2 instance Connect
Command: 
>>sudo apt update
>>sudo apt upgrade -y
Install Node.js
>>curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
Screenshot
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/f79d3d7f-9349-4a3d-a93b-bfe8a1478ea3" />




Command : 
>>sudo apt install node.js -y

Gave error
<img width="536" height="203" alt="image" src="https://github.com/user-attachments/assets/16cd34a1-3914-40e3-ae3c-eb692ce9192c" />



Correction done in command
>>sudo apt install nodejs -y
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/e015622c-393d-4201-a210-bdd22d8045cb" />


Node.js installation done


>>sudo apt install nodejs -y
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/1cc07e42-f25a-49f4-a09e-f3d48114bb3e" />



Install Git
>>sudo apt update install git
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/438e9ae6-540a-4856-b23e-d9f25c457ffc" />



Close Repository
>> git clone https://github.com/UnpredictablePrashant/TravelMemory.git
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/73f2b292-dbfe-4bcc-b8c7-d6368e41bf76" />




>>cd TravelMemory
>>cd backend

Installing backend packages
>> npm install
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/aa8ac859-85a4-41af-a234-90f0e5c05646" />



Create .env file
>>sudo nano .env

Port=3000
mongodb+srv://mukesh14481_db_user:xyz@clustermukesh.yfbmva5.mongodb.net/?appName=ClusterMukesh

Now start the server:
>> sudo npm start
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/c5cd7d0d-e01a-414b-958c-7fcd4a96eff6" />



Installing PM2 for managing the server
>>sudo npm install pm2 -g
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/b0baa2b6-d839-4530-a9a6-95de5f2c1fb3" />



>>~/TravelMemory/backend$ sudo pm2 start index.js --name backend
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/c7537b6e-6a5b-42f8-88cc-1731cbbc7691" />



>>sudo pm2 save
>>sudo pm2 startup
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/13bf56be-78c8-42f2-8c5a-3895b361ba26" />



Install nginx
>>sudo apt install nginx -y
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/2a533f9a-f4d5-4e88-961d-20086da3315d" />




Configure reverse proxy
>>sudo nano /etc/nginx/sites-available/default
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/5acee222-2bd4-485e-85e7-93f12e54b4b7" />




Restart Nginx

>>sudo nginx -t
>>sudo systemctl restart nginx


Now tried accessing the public ip and it gave error
Cannot GET /
<img width="358" height="76" alt="image" src="https://github.com/user-attachments/assets/d4cd2b5b-d05c-41c8-bf4f-b9e4e7d7dc59" />


FIxing it >>nano index.js
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/baece661-de52-41a9-b9e8-ec446a6a6f87" />




 Backend installation complete
<img width="368" height="154" alt="image" src="https://github.com/user-attachments/assets/ad339346-d63b-406c-b572-1130e9631541" />


TASK 2: Frontend + Backend connection

Launch new instance: frontend-server-1
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/a2d1031e-2531-4d27-92e1-0b47f6a62a09" />





Install packages

Commands:
>>sudo apt update -y
>>sudo apt install nginx git -y
>>curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
>>sudo apt install nodejs -y

<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/dbfb141f-7df2-4dfa-a9bd-e13b2878a818" />

<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/827376a5-db76-4929-a740-51efea4c2fce" />





Clone repository

>>git clone https://github.com/UnpredictablePrashant/TravelMemory.git

Change to frontend directory

Install npm
>>sudo npm install 
<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/ea6f9a11-8c1a-474e-9808-48b6672ddc84" />



Update urls.js
>> nano src/urls.js

<img width="383" height="126" alt="image" src="https://github.com/user-attachments/assets/b954c368-e4ce-49bf-b292-1ba964645052" />



npm run build
<img width="554" height="428" alt="image" src="https://github.com/user-attachments/assets/4c802567-77d4-49c8-abb9-839c3cd8f2be" />




Deploy built to nginx
>>sudo rm -rf /var/www/html/*
>>sudo cp -r build/* /var/www/html/


Restart nginx
>>sudo systemctl restart nginx

Access frontend with public url
<img width="315" height="141" alt="image" src="https://github.com/user-attachments/assets/3dfdb68d-66b7-4aa4-95d2-fcd0965591b4" />





TASK 3

Launch one more server of backend and frontend each

For this I created and image of both the servers and then launched the new EC2 instances so that all installations are as it is in the new servers
<img width="553" height="148" alt="image" src="https://github.com/user-attachments/assets/412bc11a-965e-4da4-a41b-06261834d50c" />




Load balancer setup

<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/d48fb593-4071-4b28-9735-ab7c731e2b6f" />

<img width="554" height="312" alt="image" src="https://github.com/user-attachments/assets/9edc6fa4-bd1a-4815-aba6-e18536823dfa" />







Edit listener>> Add rulefor Path /api/* forward to backed-target-group
<img width="553" height="252" alt="image" src="https://github.com/user-attachments/assets/4cea5441-119d-499b-99f1-802cf1b68dae" />

<img width="553" height="221" alt="image" src="https://github.com/user-attachments/assets/90ed785b-fbbb-41e0-8649-02c1ab155095" />





Load balancer added with listner and security groups. LB url is working properly

<img width="554" height="130" alt="image" src="https://github.com/user-attachments/assets/d410c660-2557-408b-9050-76abcf373397" />



I have domain in Hostinger so made the following changes to it
<img width="553" height="209" alt="image" src="https://github.com/user-attachments/assets/2dca9672-1f35-4c55-b2b5-1c773e5ea26f" />



Then tried fixing the domain resolution at nginx
>>sudo nano /etc/nginx/sites-available/default

server {
    listen 80;
    server_name menwomenkidsworld.com www.menwomenkidsworld.com;

    location / {
        proxy_pass http://localhost:3000;
    }
}

>>sudo nginx -t
>>sudo systemctl restart nginx

But could not

Task 4 of domain addition is not completed. Sorry. All other tasks done as required
