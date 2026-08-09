<div align="center">

# 💾 AWS EBS — Practical 4

### ⚡ Study and Implement Working with EBS

<p>
  <img src="https://img.shields.io/badge/AWS-EBS-orange?style=for-the-badge&logo=amazon-aws&logoColor=white" />
  <img src="https://img.shields.io/badge/Storage-gp3-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/EC2-Storage-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/M.Tech-CSE-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Practical-04-critical?style=for-the-badge" />
</p>

<p><b>Create and attach an Amazon Elastic Block Store (EBS) volume to an EC2 instance.</b></p>

<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=140&section=header&text=Amazon%20EBS&fontSize=48&fontAlignY=35&animation=fadeIn" width="100%"/>

</div>

---

# 🎯 Aim

> To create and attach an **Amazon Elastic Block Store (EBS)** volume to an EC2 instance.

---

# 🚀 Procedure

## Step 1: Open EBS

Go to:

```text
EC2 → Elastic Block Store → Volumes
```

---

## Step 2: Create Volume

Click:

```text
Create volume
```

Example:

```text
Volume Type: gp3
Size: 10 GiB
Availability Zone: Same AZ as EC2
```

Click:

```text
Create volume
```

---

## Step 3: Attach Volume

1. Select the volume.
2. Click **Actions**.
3. Select **Attach volume**.
4. Select your EC2 instance.
5. Attach.

---

## Step 4: Login to EC2

```bash
ssh -i MTech-Key.pem ec2-user@PUBLIC-IP
```

Check disks:

```bash
lsblk
```

You may see a new device such as:

```text
nvme1n1
```

---

## Step 5: Format Volume

> ⚠️ Only do this if the volume is new and contains no data.

```bash
sudo mkfs -t xfs /dev/nvme1n1
```

---

## Step 6: Create Mount Directory

```bash
sudo mkdir /data
```

---

## Step 7: Mount

```bash
sudo mount /dev/nvme1n1 /data
```

Check:

```bash
df -h
```

---

## Step 8: Create File

```bash
sudo touch /data/test.txt
```

```bash
echo "EBS Storage Test" | sudo tee /data/test.txt
```

---

# 🧊  EBS Architecture

```mermaid
flowchart LR

    A["☁️ AWS Cloud"] --> B["🖥️ EC2 Instance"]

    B --> C["💾 EBS Volume"]

    C --> D["📦 10 GiB"]
    C --> E["⚡ gp3"]
    C --> F["📍 Same Availability Zone"]

    B --> G["📂 /data"]
    G --> H["📄 test.txt"]

    style A fill:#232f3e,color:#fff
    style B fill:#ff9900,color:#000
    style C fill:#2196f3,color:#fff
    style D fill:#9c27b0,color:#fff
    style E fill:#03a9f4,color:#fff
    style F fill:#607d8b,color:#fff
    style G fill:#009688,color:#fff
    style H fill:#4caf50,color:#fff
```

---

# 🔄  Storage Flow

```text
                         ☁️ AWS CLOUD
                              │
                              ▼
                  ┌──────────────────────┐
                  │    🖥️ EC2 INSTANCE   │
                  │                      │
                  │    MTech-EC2         │
                  │    🐧 Linux          │
                  └──────────┬───────────┘
                             │
                        ⚡ ATTACH
                             │
                             ▼
                  ╔══════════════════════╗
                  ║      💾 EBS          ║
                  ║                      ║
                  ║      gp3             ║
                  ║      10 GiB          ║
                  ║                      ║
                  ╚══════════╤═══════════╝
                             │
                        🔧 FORMAT
                             │
                             ▼
                       📂 /data
                             │
                             ▼
                       📄 test.txt
                             │
                             ▼
                    💾 EBS STORAGE
```

---

<div align="center">

# 🧊 Visualization

```text
                 ╭──────────────────────────╮
                ╱                          ╱│
               ╱        🖥️ EC2           ╱ │
              ╱        MTech-EC2        ╱  │
             ╰──────────────────────────╯   │
             │                              │
             │                              │
             │          ⚡                  │
             │         ATTACH               │
             │                              │
             ╰──────────────┬───────────────╯
                            │
                            ▼
                  ╭──────────────────╮
                 ╱                  ╱│
                ╱      💾 EBS      ╱ │
               ╱      gp3          ╱  │
              ╰──────────────────╯   │
              │     10 GiB          │
              │                     │
              │       📂 /data      │
              │                     │
              ╰─────────────────────╯
```

---

# 📝 Result

> **An EBS volume was successfully created, attached to EC2, formatted, mounted, and used for data storage.**
<div align="center">

# 🎉 Practical 4 Completed Successfully

---

### 💾 AWS EBS | M.Tech CSE Practical

<p>
  <img src="https://img.shields.io/badge/AWS-EBS-orange?style=flat-square&logo=amazon-aws" />
  <img src="https://img.shields.io/badge/Storage-gp3-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Volume-10%20GiB-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/Practical-Completed-success?style=flat-square" />
</p>
<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer" width="100%"/>

</div>
</div>
