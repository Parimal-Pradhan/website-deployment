# Launch Instance

## Step : -1

### Enter Name and Select Ubuntu AMI

<img width="1901" height="687" alt="image" src="https://github.com/user-attachments/assets/91f8814b-4bdb-420d-9dcb-3d2407d2819e" />

## Step : -2
### Select Instance type and Create Key Pair

<img width="1912" height="596" alt="image" src="https://github.com/user-attachments/assets/59de9ef0-be17-4861-9db3-6ff6a7ced460" />

## Step : -3
### Allow port 8080 for Jenkins

<img width="1885" height="418" alt="image" src="https://github.com/user-attachments/assets/2807e20e-6f2e-4582-ba69-47300c1ae6d0" />

## Step : -4
### Enter Storage

<img width="1905" height="408" alt="image" src="https://github.com/user-attachments/assets/c2cff1ba-3355-4650-b797-7017f3fab005" />

## Step : -5
### Launch Instance 

<img width="1913" height="281" alt="image" src="https://github.com/user-attachments/assets/1aaf8047-2f68-473f-98d2-7a6746c9c90f" />

## Step : -6
### Select Instance and connect 

<img width="1596" height="317" alt="image" src="https://github.com/user-attachments/assets/bba35bd0-af89-48b7-9653-c9c1af8eea5f" />

## Step : -7
### Select EC2 Instance connect option

<img width="1842" height="672" alt="image" src="https://github.com/user-attachments/assets/03bbba7c-6381-48ac-ac1b-9a2004d1f04c" />

## Step : -8
### Update the packages

<img width="1918" height="282" alt="image" src="https://github.com/user-attachments/assets/05fbadfe-5517-447b-86db-552cbacee239" />

## Step : -9
### a) Insall Apache 

```bash id="inst3"
sudo apt install apache2 -y
```
### b) Start Apache:

```bash id="inst3"
sudo systemctl enable apache2
sudo systemctl start apache2
```
### c) Verify:

```bash id="inst3"
sudo systemctl status apache2
```

You should see:

active (running)

Open in a browser:

http://PUBLIC-IP:80

You should see the Apache default page.

### d)  Remove Default Website
sudo rm -rf /var/www/html/*

### e) Change the owner of a file

sudo chown -R jenkins:jenkins /var/www/html


<img width="1650" height="103" alt="image" src="https://github.com/user-attachments/assets/d6a0b3ec-16ef-4bc9-98bb-4a629dc923df" />

## Step : -10
### Copy public ip and paste in browser like below , To check apache install or not.

<img width="1535" height="632" alt="image" src="https://github.com/user-attachments/assets/1010476a-8c1d-4020-9be3-a7629316e4f7" />

## Step : -11
### Install java

<img width="1637" height="147" alt="image" src="https://github.com/user-attachments/assets/196a6ade-7819-4321-aee3-76c6f7d216e5" />

## Step : -12
### Check Java version

<img width="1667" height="187" alt="image" src="https://github.com/user-attachments/assets/9b4834fd-7d43-425f-abd2-08cf3e09e3ec" />


## Step : -11
### Install Jenkins

<img width="1622" height="225" alt="image" src="https://github.com/user-attachments/assets/6066f0b1-ffb9-45d7-ab37-94fd5cb07971" />

## Step : -12
### Check Jenkins version

<img width="1641" height="142" alt="image" src="https://github.com/user-attachments/assets/ca21e546-ae14-4eb4-ae0a-13b62df16c21" />

## Step : -13
### Copy Public ip and Enter port like below:

<img width="1583" height="935" alt="image" src="https://github.com/user-attachments/assets/89a3065f-e2d0-4508-8fe1-eca6c9ced82c" />

## Step : -14
### cat Admin password from EC2 where jenkins installed check below image

<img width="1651" height="136" alt="image" src="https://github.com/user-attachments/assets/01bc564f-3b9d-4a59-8e66-e1be2193bc9e" />

## Step : -15
### Copy and paste password to Jenkins login page and press continue

<img width="1647" height="927" alt="image" src="https://github.com/user-attachments/assets/62f02dbe-3b1b-4c2f-a183-de8d4184af1d" />

## Step : -16
### Select option Install suggested plugins

<img width="1648" height="917" alt="image" src="https://github.com/user-attachments/assets/7d17f42d-71ed-4f84-a1f3-25906f046b7f" />

### Wait till plugins get installed
<img width="1632" height="960" alt="image" src="https://github.com/user-attachments/assets/64a41b8a-f06f-49bc-a674-03617212b0c1" />

## Step : -17
### Create User and set password and click and continue

<img width="1673" height="952" alt="image" src="https://github.com/user-attachments/assets/f530e2f8-a5e8-4974-bed7-26e38785b94f" />

## Step : -18
### Jenkins is ready

<img width="1640" height="947" alt="image" src="https://github.com/user-attachments/assets/914b3b7f-8990-48d2-a60d-e274f8dc7439" />

## Step : -19
### Jenkins Dashboard is ready

<img width="1807" height="925" alt="image" src="https://github.com/user-attachments/assets/abe02cfd-a675-4d49-86d2-5c30196da0b2" />

## Step : -20
### Add Github Credentials :
Go to Manage Jenkins --> Select Credentials --> Add Github Username and Password 

<img width="1911" height="648" alt="image" src="https://github.com/user-attachments/assets/67ae22aa-349c-4586-8392-40ef778baaab" />

<img width="845" height="817" alt="image" src="https://github.com/user-attachments/assets/1e31fa30-9c1f-4b6c-a58e-b7426b4471ed" />

## Step : -21
### Create webhook and jenkins url to github webhook :
Go to Github --> Settings --> Click on webhook --> Add Payload URL *http://<ip>:8080/github-webhook/   --> Select content type --> application/json and save or update webhook

<img width="1720" height="773" alt="image" src="https://github.com/user-attachments/assets/0e0b4d79-c0dc-41dc-928a-a2a641de137b" />

<img width="1835" height="768" alt="image" src="https://github.com/user-attachments/assets/265b22b2-462a-4d65-97d5-8af5d9db506a" />

## Step : -22
### Create Pipeline for deployment
Go to Jenkins Dashboard --> New Item

<img width="1743" height="768" alt="image" src="https://github.com/user-attachments/assets/35d5d6b5-553c-4165-99b7-3ea2c422a155" />

Enter an item name --> Select Pipeline --> click ok

<img width="1883" height="842" alt="image" src="https://github.com/user-attachments/assets/75fabb48-15f4-499c-953b-2da1c5189dc2" />

## Step : -23
### Select script from SCM option

<img width="1901" height="726" alt="image" src="https://github.com/user-attachments/assets/f3c0c3eb-7f4f-4764-8085-aca5bb5b1f5f" />

Script Path -- > Jenkinsfile
SCM --> Git 
Repository URL --> Enter repository url

<img width="1875" height="757" alt="image" src="https://github.com/user-attachments/assets/7fbbfd84-d52d-40a4-9868-9c7957dd2a03" />

select credentials:

<img width="1840" height="801" alt="image" src="https://github.com/user-attachments/assets/a7869698-f709-43e8-8674-8a2fecc40904" />

Enter branch name as per repository : Main or Master

<img width="1896" height="661" alt="image" src="https://github.com/user-attachments/assets/07c603e6-a544-4846-96a8-f693831a25ef" />

Script Path  --> Jenkinsfile

Click On Save and Apply

<img width="1892" height="763" alt="image" src="https://github.com/user-attachments/assets/b9c02d5e-4d8a-40da-a013-b30ae27c96f3" />


## Step : -24
## Final Deployment Stages
Click on Build Now for Manually building pipeline or Make change in code and push in github 

<img width="1907" height="493" alt="image" src="https://github.com/user-attachments/assets/87692d83-f8bb-45b5-8cf7-096c8ed0c184" />

## Step : -25
## Paste public ip with port on webbrowser to check application deployed or not

<img width="1833" height="878" alt="image" src="https://github.com/user-attachments/assets/74350a88-f803-4118-8d6b-bee95c5c59d9" />




