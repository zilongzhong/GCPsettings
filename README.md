# Setup Guide for how to ssh Virtual Instance on Google Cloud Platform

This guide provides instructions on how to set up a virtual machine (VM) with GPU capabilities on Google Cloud Platform. This setup is ideal for applications that require heavy computational power such as deep learning and video processing.

## Prerequisites

- Google Cloud Platform account
- Basic understanding of command-line interfaces and cloud computing

## Step 1: Generate SSH key

''
ssh-keygen -t rsa -b 2048 -f ~/.ssh/gcp-lesson-120 -C my-username
''








## Step 1: Create a New VM Instance

1. **Log in to Google Cloud Console**: Open your web browser and navigate to the [Google Cloud Console](https://console.cloud.google.com/). Log in using your Google account.

2. **Go to the Compute Engine**: On the left-hand menu, click on “Compute Engine” and then “VM instances”.

3. **Create Instance**: Click on “Create Instance”.
   - Name your instance.
   - Choose a region and zone where GPU devices are available.

## Step 2: Configure Machine Type and GPU

1. **Machine Type**: Select a machine type based on your computational needs. For GPU-intensive tasks, it's recommended to select a high-memory or high-CPU machine type.

2. **Add GPUs**:
   - Under the “Machine configuration” section, click on “CPU and GPU”.
   - In the GPU type dropdown, select the type of GPU you need (e.g., NVIDIA Tesla T4).
   - Specify the number of GPUs.
   - Accept any necessary GPU quotas and terms of service.

## Step 3: Boot Disk and Network Settings

1. **Boot Disk**: Click on “Change” for the Boot Disk. Select an image suitable for your applications (e.g., a deep learning image that comes with pre-installed frameworks like TensorFlow or PyTorch).

2. **Firewall**: Under the “Firewall” section, ensure that both “Allow HTTP traffic” and “Allow HTTPS traffic” are checked to enable web access.

3. **Networking**: Configure network settings as required for your project.

## Step 4: Finalize and Launch

1. Review all settings. Click on “Create” to deploy your VM.

2. Once the VM is set up, connect to it using SSH by clicking the SSH button in the VM instances list.

## Step 5: Install Required Libraries and Frameworks

Once connected to your VM, you might need to install additional software or libraries specific to your project.

```bash
sudo apt-get update
sudo apt-get install -y your-required-package
