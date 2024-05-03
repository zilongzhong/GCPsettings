# Setup Guide for how to ssh Virtual Machine on Google Cloud Platform

This guide provides instructions on how to set up a virtual machine (VM) with GPU capabilities on Google Cloud Platform. This setup is ideal for applications that require heavy computational power such as deep learning and video processing.

## Prerequisites

- Google Cloud Platform account
- Basic understanding of command-line interfaces and cloud computing

## Step 1: Generate SSH key

Please run the following command on your local PC, and replace 'gcp-test' with your SSH key name:

```bash
ssh-keygen -t rsa -b 2048 -f ~/.ssh/gcp-test-120 -C my-username
```
Then, you should have a private key ~/.ssh/gcp-test-120, and a public ~/.ssh/gcp-test-120.pub

## Step 2: Greate a VM instance on GCP 

<div style="text-align: center;">
    <img src="figures/PC_Cmaps1.png" height="600" />
</div>

When creating a VM on GCP, use the 'Security' section to add your public SSH key as shown in the above figure, which you can use to access the VM from your local PC. Then, you can access the GCP VM through the command as follows from your local machine. Please replace `GCPname@XXX.XXX.XX.XXX` to your GCP account and the IP of the VM:

```bash
ssh -i ~/.ssh/gcp-test-120 GCPname@XXX.XXX.XX.XXX
```

## Step 3: Greate Cloud Storage Buckets



## Step 4: Mount Cloud Storage Buckets on GCP VM



## Step 5: Set remote Jupyter Lab



## Step 6: Set remote VS Code

Set the config file in the .ssh path accordingly. Specifically, make sure to update GCPname, XXX.XXX.XX.XXX, and /path/to/your/public/key.pub properly:

```bash
Host GCP-test
  HostName XXX.XXX.XX.XXX
  User GCPname
  IdentityFile /path/to/your/public/key.pub
```

## References

https://www.youtube.com/watch?v=elXJCyBSHUk
