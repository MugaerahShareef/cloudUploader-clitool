# Azure CLI Upload Tool

## Introduction

This tool automates the installation of Azure CLI and facilitates the secure upload of files to an Azure Storage Blob container. It includes two main scripts:

1. **Setup Script:** Installs or updates Azure CLI and logs in using a service principal.
2. **Cloud Upload Script:** Validates file access and uploads the file to an Azure Storage Blob container.

---

## Prerequisites

- **Azure Subscription:** Ensure you have an active Azure subscription.
- **Service Principal:** Obtain the credentials for an Azure Service Principal (Application ID, Secret, and Tenant ID).
- **Azure CLI:** This tool installs or updates Azure CLI if not already installed.

---

## How to Use

### Step 1: Setup

1. **Run the Setup Script**

    The `setup` script installs or updates the Azure CLI and logs you into Azure using a Service Principal.

    ```bash
    ./setup
    ```

    - **Enter Service Principal Credentials:** When prompted, provide your Application ID, Secret, and Tenant ID.
    - **Successful Login:** If the credentials are correct, you will be logged in, and the script will confirm the Service Principal name.

2. **Errors Handling:**
   - If the Azure CLI installation fails, the script will notify you.
   - If the login fails due to incorrect credentials, an error message will be displayed.

### Step 2: Uploading a File

1. **Run the Cloud Upload Script**

    The `cloudupload` script checks file accessibility and uploads it to the specified Azure Storage Blob container.

    ```bash
    ./cloudupload <path_to_your_file>
    ```

    - **File Check:** The script first verifies if the file exists and checks access permissions.
    - **Blob Existence:** If a blob with the same name already exists in the container, the upload is aborted to prevent overwriting.
    - **Upload Completion:** If the upload is successful, a confirmation message will be displayed. If not, an error message will appear.

2. **Errors Handling:**
   - If the file is not readable or does not exist, the script will notify you.
   - If the upload fails, the script will indicate that the process was unsuccessful.

---

## Important Notes

- **File Path:** Ensure that the file path provided to the `cloudupload` script is correct and accessible.
- **Permissions:** Make sure the user executing the script has sufficient permissions to run scripts and access Azure resources.

---

## Conclusion

This tool simplifies the process of setting up Azure CLI and securely uploading files to Azure Blob Storage. It provides clear instructions and error messages, making it accessible to both technical and non-technical users.
