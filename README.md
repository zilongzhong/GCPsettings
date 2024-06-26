# Setup Guide for how to ssh Virtual Machine on Google Cloud Platform

This guide provides instructions on how to set up a virtual machine (VM) with GPU capabilities on Google Cloud Platform. This setup is ideal for applications that require heavy computational power such as deep learning and video processing.

## Prerequisites

- Google Cloud Platform account
- Basic understanding of command-line interfaces and cloud computing

## Step 1: Generate SSH key

Please run the following command on your local PC, and replace 'gcp-test' with your SSH key name:

```bash
ssh-keygen -t rsa -b 2048 -f ~/.ssh/gcp-test -C my-username
```
Then, you should have a private key ~/.ssh/gcp-test, and a public ~/.ssh/gcp-test.pub
Make sure that the ssh is added as an allowed ssh key in VM, and make sure my-username is the same as your username of GCP VM

## Step 2: Greate a VM instance on GCP 

<div style="text-align:center;">
  <img src="gcp_vm.png" height="600"/>
</div>

When creating a VM on GCP, use the 'Security' section to add your public SSH key as shown in the above figure, which you can use to access the VM from your local PC. Then, you can access the GCP VM through the command as follows from your local machine. Please replace `GCPname@XXX.XXX.XX.XXX` to your GCP account and the IP of the VM:

```bash
ssh -i ~/.ssh/gcp-test-120 GCPname@XXX.XXX.XX.XXX
```

## Step 3: Greate Cloud Storage Bucket

Then, create a Cloud Storage Bucket named 'gcp_bucket01' as below, which you can replace with another name.
<div style="text-align:center;">
  <img src="gcp_bucket.png" height="300"/>
</div>


<!-- ## Step 4: Mount Cloud Storage Buckets on GCP VM -->

## Step 4: Downlaod the Nvidia Driver and Install it on GCP VM

[Nvidia Driver Website](https://www.nvidia.com/download/index.aspx)


## Step 5: Install miniconda on GCP VM and transfer zipped Environment Package

Please refere to [Miniconda Installation](https://docs.anaconda.com/free/miniconda/index.html)

The zipped Conda Environment can be downloaded from [DoogleDrive](https://drive.google.com/file/d/1FjM1vYWYD46ucTaniQ4vEoOIWSOH2ZUE/view?usp=drive_link)


## Step 6: Set remote Jupyter Lab

[Remote Jupyter Lab Setting](https://medium.com/analytics-vidhya/setting-up-jupyter-lab-instance-on-google-cloud-platform-3a7acaa732b7)

## Step 7: Set remote VS Code

After installing VS Code on your local PC, set the config file in the .ssh path accordingly. Specifically, make sure to update GCPname, XXX.XXX.XX.XXX, and /path/to/your/public/key.pub properly:

```bash
Host GCP-test
  HostName XXX.XXX.XX.XXX
  User GCPname
  IdentityFile /path/to/your/public/key.pub
```

## References

1. [How to set ssh for GCP](https://www.youtube.com/watch?v=elXJCyBSHUk)

2. [Mount a Cloud Storage bucket on GCP VM](https://cloud.google.com/storage/docs/gcsfuse-quickstart-mount-bucket)

3. [Set Globus for Cloud Storage](https://docs.globus.org/premium-storage-connectors/v5.4/google-cloud-storage/)

4. [Miniconda Installation](https://docs.anaconda.com/free/miniconda/index.html)

5. [VS Code Installation](https://code.visualstudio.com/docs/setup/linux)

6. [Remote Jupyter Lab Setting](https://medium.com/analytics-vidhya/setting-up-jupyter-lab-instance-on-google-cloud-platform-3a7acaa732b7)
