# Setup Guide for how to ssh Virtual Instance on Google Cloud Platform

This guide provides instructions on how to set up a virtual machine (VM) with GPU capabilities on Google Cloud Platform. This setup is ideal for applications that require heavy computational power such as deep learning and video processing.

## Prerequisites

- Google Cloud Platform account
- Basic understanding of command-line interfaces and cloud computing

## Step 1: Generate SSH key

In the following command, please replace 'gcp-lesson-120' with your ssh key name:  

```bash
ssh-keygen -t rsa -b 2048 -f ~/.ssh/gcp-test-120 -C my-username
```
Then, you should have a private key ~/.ssh/gcp-test-120, and a public ~/.ssh/gcp-test-120.pub

## Step 2: Greate a VM instance on GCP 

When creating a VM on GCP, use the 'Security' section to add your public SSH key, which you can use to access the VM from your local PC. Then, you can access the GCP VM through a command from your local machine.:

```bash
ssh -i ~/.ssh/gcp-test-120 name@XXX.XXX.XX.XXX
```

