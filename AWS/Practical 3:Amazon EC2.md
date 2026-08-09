<div align="center">

# ☁️ AWS EC2 — Practical 3

### 🖥️ Implementation of Amazon EC2

<p>
  <img src="https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazon-aws&logoColor=white" />
  <img src="https://img.shields.io/badge/Virtual-Machine-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/M.Tech-CSE-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Practical-03-success?style=for-the-badge" />
</p>

<p><b>Launch and configure an Amazon EC2 virtual machine.</b></p>

<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=130&section=header&text=Amazon%20EC2&fontSize=45&fontAlignY=35&animation=fadeIn" width="100%"/>

</div>

---

# 🎯 Aim

> To launch and configure an **Amazon EC2 virtual machine**.

---

# 🚀 Procedure

## Step 1

Open:

```text
AWS Console → EC2
```
---

## Step 2: Launch Instance

Click:

```text
Launch Instance
```

Enter:

```text
Name: MTech-EC2
AMI: Amazon Linux
Instance Type: t3.micro
```

---

## Step 3: Key Pair

Create/select:

```text
MTech-Key
```

Download the:

```text
MTech-Key.pem
```

Store the `.pem` file securely.

---

## Step 4: Security Group

Allow:

```text
SSH  – TCP – 22
HTTP – TCP – 80
```

---

## Step 5: Launch

Click:

```text
Launch instance
```

Wait until:

```text
Instance state = Running
```

---

## Step 6: Connect

```bash
ssh -i MTech-Key.pem ec2-user@PUBLIC-IP
```

---

## Step 7: Check System

### Check Kernel and System Information

```bash
uname -a
```

### Check Operating System

```bash
cat /etc/os-release
```

### Check Disk Usage

```bash
df -h
```

### Check Memory

```bash
free -h
```

---

## Step 8: Install Web Server

```bash
sudo dnf install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

---

# 🔄 EC2 Implementation Flow

```mermaid
flowchart LR

    A["☁️ AWS Console"] --> B["🖥️ EC2"]
    B --> C["🚀 Launch Instance"]
    C --> D["🐧 Amazon Linux"]
    D --> E["🔑 MTech-Key"]
    E --> F["🛡️ Security Group"]
    F --> G["▶️ Instance Running"]
    G --> H["🔐 SSH Connection"]
    H --> I["⚙️ System Check"]
    I --> J["🌐 Install Apache"]

    style A fill:#232f3e,color:#fff
    style B fill:#ff9900,color:#000
    style C fill:#2196f3,color:#fff
    style D fill:#607d8b,color:#fff
    style E fill:#9c27b0,color:#fff
    style F fill:#f44336,color:#fff
    style G fill:#4caf50,color:#fff
    style H fill:#03a9f4,color:#fff
    style I fill:#795548,color:#fff
    style J fill:#009688,color:#fff
```

---

<div align="center">

### 🖥️ EC2 Instance

```text
┌──────────────────────────────────────────┐
│              ☁️ AWS EC2                  │
│                                          │
│        🖥️ MTech-EC2                     │
│                                          │
│        🐧 Amazon Linux                   │
│        ⚡ t3.micro                       │
│                                          │
│        🔑 MTech-Key                      │
│        🛡️ SSH : 22                      │
│        🌐 HTTP : 80                      │
│                                          │
│        🟢 Instance Running               │
│                                          │
└──────────────────────────────────────────┘
```

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer" width="100%"/>

</div>

---

# 📝 Result

> **An EC2 virtual machine was successfully launched, accessed through SSH, and configured as a web server.**

<div align="center">

# 🎉 Practical 3 Completed Successfully

---

### 🖥️ AWS EC2 | M.Tech CSE Practical

<p>
  <img src="https://img.shields.io/badge/AWS-EC2-orange?style=flat-square&logo=amazon-aws" />
  <img src="https://img.shields.io/badge/Virtual-Machine-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Apache-Running-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Practical-Completed-success?style=flat-square" />
</p>

</div>

