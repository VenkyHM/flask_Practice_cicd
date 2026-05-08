## Step:1 Repo Fork to Github
---

 ```bash 
git clone https://github.com/VenkyHM/flask_Practice_cicd.git
cd flask_Practice_cicd
````
----

## Step:2 Testing the application locally.
----

<img width="1861" height="1045" alt="image" src="https://github.com/user-attachments/assets/59f52fc9-dab0-406a-93c4-75f748c9660b" />

---
<img width="1907" height="1039" alt="image" src="https://github.com/user-attachments/assets/3ab80a97-4d6e-4bb9-907a-b9330a2b032b" />

---
<img width="1910" height="1040" alt="image" src="https://github.com/user-attachments/assets/f75e296d-134c-4b85-950e-6d4827224fbd" />

---

## Checking pytest on local
<img width="1485" height="730" alt="image" src="https://github.com/user-attachments/assets/bfbbf294-0b0e-4b30-84dd-9db6605041f9" />

---

## Step:3 Github branching setup.
```bash
git checkout -b staging
git push origin staging
git checkout main
```
<img width="1464" height="469" alt="image" src="https://github.com/user-attachments/assets/7a66f55c-5616-4835-ba22-584662607443" />

---
<img width="1904" height="954" alt="image" src="https://github.com/user-attachments/assets/181930a9-f058-441f-9b87-e41250fe9ae6" />

---

## Step:4 Lanching AWS EC2 and Jenkins Installation

```bash
Installed all the dependecies on ec2
sudo dnf update -y
sudo dnf install java-17-amazon-corretto -y

sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

sudo dnf install jenkins -y

sudo systemctl enable jenkins
```
## Step-5 Accessing Jenkins and Building the test case.

<img width="1451" height="930" alt="image" src="https://github.com/user-attachments/assets/966f0c18-7dce-4c81-9948-7ed3f6b39951" />

---
<img width="1869" height="1031" alt="image" src="https://github.com/user-attachments/assets/b77fb65c-9d57-40e7-9123-a817f7e9c3f6" />

---
<img width="1006" height="773" alt="image" src="https://github.com/user-attachments/assets/9e9fa2f6-1bc5-482d-aa7b-732cd5f5da7a" />

# Accessing the Flask app through EC2 Instance 
<img width="1912" height="1030" alt="image" src="https://github.com/user-attachments/assets/0173943b-9e9e-4489-8e9d-f5b200bed14e" />

---
<img width="1910" height="1076" alt="image" src="https://github.com/user-attachments/assets/d6f5af8a-7831-4b2e-8e16-1dc8f546ce23" />

## Step-6 Configuring the email notifiaction whenever the pipeline is triggering new build when new changes are made.

---
<img width="1906" height="1034" alt="image" src="https://github.com/user-attachments/assets/7a9e024b-cc4e-4d6c-a88e-d10334d1bc84" />

---
<img width="1570" height="891" alt="image" src="https://github.com/user-attachments/assets/5561b653-ea6a-4ef8-a9d5-f4063fb9571f" />

# TASK 2: GitHub Actions CI/CD

## Step- Added github secrets
---
<img width="1917" height="957" alt="image" src="https://github.com/user-attachments/assets/5f0e6409-878b-48f9-8a6c-c40fc5f31349" />

---
## Step-8 Code pushing from the staging branch
```bash
git add .
git commit -m "Added GitHub Actions CI/CD pipeline flask app"
git push origin staging
```
----
<img width="1917" height="946" alt="image" src="https://github.com/user-attachments/assets/07547d83-0676-4f11-93c2-11983df201f0" />

---
<img width="1915" height="951" alt="image" src="https://github.com/user-attachments/assets/e97d5670-3c15-4c57-a82b-8e39bbd8bae5" />





















