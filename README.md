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



Command : 
>>sudo apt install node.js -y

Gave error



Correction done in command
>>sudo apt install nodejs -y


Node.js installation done


>>sudo apt install nodejs -y



Install Git
>>sudo apt update install git



Close Repository
>> git clone https://github.com/UnpredictablePrashant/TravelMemory.git




>>cd TravelMemory
>>cd backend

Installing backend packages
>> npm install



Create .env file
>>sudo nano .env

Port=3000
mongodb+srv://mukesh14481_db_user:xyz@clustermukesh.yfbmva5.mongodb.net/?appName=ClusterMukesh

Now start the server:
>> sudo npm start



Installing PM2 for managing the server
>>sudo npm install pm2 -g



>>~/TravelMemory/backend$ sudo pm2 start index.js --name backend



>>sudo pm2 save
>>sudo pm2 startup



Install nginx
>>sudo apt install nginx -y




Configure reverse proxy
>>sudo nano /etc/nginx/sites-available/default




Restart Nginx

>>sudo nginx -t
>>sudo systemctl restart nginx


Now tried accessing the public ip and it gave error
Cannot GET /

FIxing it >>nano index.js




 Backend installation complete


TASK 2: Frontend + Backend connection

Launch new instance: frontend-server-1





Install packages

Commands:
>>sudo apt update -y
>>sudo apt install nginx git -y
>>curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
>>sudo apt install nodejs -y







Clone repository

>>git clone https://github.com/UnpredictablePrashant/TravelMemory.git

Change to frontend directory

Install npm
>>sudo npm install 



Update urls.js
>> nano src/urls.js




npm run build




Deploy built to nginx
>>sudo rm -rf /var/www/html/*
>>sudo cp -r build/* /var/www/html/


Restart nginx
>>sudo systemctl restart nginx

Access frontend with public url





TASK 3

Launch one more server of backend and frontend each

For this I created and image of both the servers and then launched the new EC2 instances so that all installations are as it is in the new servers




Load balancer setup









Edit listener>> Add rulefor Path /api/* forward to backed-target-group






Load balancer added with listner and security groups. LB url is working properly




I have domain in Hostinger so made the following changes to it



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
