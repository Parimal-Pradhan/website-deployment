# Real Estate - Website Deployment

<img width="1693" height="929" alt="ChatGPT Image Jul 17, 2026, 02_20_30 PM" src="https://github.com/user-attachments/assets/95b283dc-5cb6-4688-8459-e9a89cad4a71" />


## Step by Step Flow


```text
Developer
    │
    ▼
Write HTML Code (index.html)
    │
    ▼
Git (Local Repository)
    │
git add
git commit
git push
    │
    ▼
GitHub Repository
    │
Webhook
    ▼
Jenkins
    │
Clone Repository
    │
(Optional: Basic Validation)
    │
Copy Website Files
    │
SSH
    ▼
AWS EC2
(Apache2 Installed)
    │
/var/www/html
    │
    ▼
Website Live
```

---

# Enterprise Implementation Plan

## Sprint 0 – Project Setup

### Goal

Create the project and push it to GitHub.

Tasks

* Create GitHub repository
* Clone repository
* Create project structure
* Add README
* First commit
* Push to GitHub

**Git Concepts**

* git init
* git clone
* git add
* git commit
* git push

---

## Sprint 1 – Home Page

### Goal

Develop the homepage.

Tasks

* Create `index.html`
* Add header
* Add navigation
* Add hero section
* Add footer

**Git Concepts**

* Feature branch
* Commit messages
* Push feature branch
* Pull Request
* Merge

---

## Sprint 2 – Improve Website

Tasks

* CSS
* Images
* Responsive design

**Git Concepts**

* Git fetch
* Git pull
* Git merge

---

## Sprint 3 – Bug Fix

Example

> Navigation menu not aligned.

Developer creates

```text
bugfix/navbar
```

Learn

* Bugfix branch
* Merge conflict
* Conflict resolution

---

## Sprint 4 – Release

Website is ready.

Learn

```bash
git tag v1.0
```

GitHub Release

```
Version 1.0
```

---

# Jenkins Phase

Now developers have completed the website.

## Sprint 5 – Jenkins Setup

Tasks

* Install Jenkins
* Install Java
* Install Git
* Install Plugins
* Connect GitHub

Pipeline

```
GitHub

↓

Jenkins

↓

Clone Repository
```

---

## Sprint 6 – Deploy to EC2

### EC2

Install Apache

```bash
sudo apt update

sudo apt install apache2 -y
```

Website Location

```text
/var/www/html
```

Configure Jenkins SSH

```
Manage Jenkins

↓

Credentials

↓

SSH Key
```

Pipeline

```
GitHub

↓

Jenkins

↓

SSH

↓

EC2

↓

Copy index.html

↓

Restart Apache
```

---

## Sprint 7 – Automatic Deployment

Developer modifies

```text
index.html
```

Commands

```bash
git add .

git commit -m "Updated Homepage"

git push
```

Automatically

```
GitHub

↓

Webhook

↓

Jenkins

↓

Clone Latest Code

↓

Copy Files

↓

EC2

↓

Website Updated
```

---

# Final Architecture

```text
+------------------+
| Developer        |
| HTML / CSS / JS  |
+------------------+
         |
         | git push
         ▼
+------------------+
| GitHub Repository|
+------------------+
         |
         | Webhook
         ▼
+------------------+
| Jenkins Server   |
| Clone Repository |
+------------------+
         |
         | SSH
         ▼
+--------------------------+
| AWS EC2                  |
| Apache2                  |
| /var/www/html            |
+--------------------------+
         |
         ▼
+--------------------------+
| Live Website             |
| http://EC2-Public-IP     |
+--------------------------+
```


<img width="1902" height="752" alt="image" src="https://github.com/user-attachments/assets/1e22efc9-7d25-4dc6-9afd-6d1a117700ba" />


