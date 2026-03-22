# AWS EC2 Forensic Investigation Lab

## Overview
This project demonstrates a cloud forensic investigation workflow in AWS. A compromised EC2 instance was identified, its EBS volume was acquired through a snapshot, and the evidence was mounted on a separate forensic workstation for examination.

## Objectives
- Create a Production Machine EC2 instance
- Create a Forensic Workstation EC2 instance
- Acquire forensic evidence from the Production Machine
- Create an EBS snapshot
- Create a new volume from the snapshot
- Attach the volume to the forensic workstation
- Mount and examine the evidence volume

## Tools Used
- AWS EC2
- AWS EBS Volumes
- AWS EBS Snapshots
- Ubuntu Linux
- PuTTY
- SSH

## Lab Workflow

### 1. Created the Production Machine
A Production Machine EC2 instance was launched in AWS to simulate the affected system.

### 2. Created the Forensic Workstation
A second EC2 instance was launched to serve as the forensic analysis workstation.

### 3. Connected to the Instance
PuTTY and SSH were used to connect securely to the instance.

### 4. Created a Snapshot of the EBS Volume
The EBS volume attached to the Production Machine was selected, and a snapshot was created to preserve the evidence.

### 5. Created a New Volume from the Snapshot
A new EBS volume was created from the snapshot to avoid modifying the original evidence.

### 6. Attached the New Volume to the Forensic Workstation
The evidence volume was attached to the forensic workstation for analysis.

### 7. Mounted and Examined the Evidence
The attached volume was mounted in Linux and prepared for forensic examination.

## Example Linux Commands
```bash
lsblk
sudo mkdir /mnt/forensic
sudo mount /dev/xvdf1 /mnt/forensic
cd /mnt/forensic
ls -la
