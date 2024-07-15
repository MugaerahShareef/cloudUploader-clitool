# **_cloudUploader-clitool_**
## - Installations
1. Make sure you have the Azure CLI installed.

2.Clone this repository to your local machine:

    git clone https://github.com/MugaerahShareef/clouduploader-clitool.git
3.Navigate to the project directory: 

    cd clouduploader
4.Make the script executable:

    chmod +x clouduploader.sh
## - Usage
### Uploading a File
To upload a file to an Azure Blob Storage container, run the following command:

    ./clouduploader.sh /path/to/your/file.txt

Replace /path/to/your/file.txt with the actual path to the file you want to upload.
### Progress Bar
Progress Bar
The script includes a progress bar to track the upload progress. It will display something like this:

    >>>                       [20%]
    >>>>>>>                   [40%]
    >>>>>>>>>>>>>>            [60%]
    >>>>>>>>>>>>>>>>>>>>>>>   [80%]
    >>>>>>>>>>>>>>>>>>>>>>>>>>[100%]
### Troubleshooting
1.If you encounter any issues related to file permissions or readability, the script will provide appropriate error messages.
2.Make sure you have the necessary permissions to execute and read the file.
### Use of Environment Variables
#### 1.Resource Group Name
-Create an environment variable for your Azure resource group name. Replace "your-resource-group" with the actual name:

    export AZURE_RESOURCE_GROUP="your-resource-group"

#### 2.Storage Account Name
-Storage Account Name:
Set an environment variable for your Azure storage account name. Replace "your-storage-account" with the actual name:

    export AZURE_STORAGE_ACCOUNT="your-storage-account"
#### 3.Container Name
-Container Name:
Define an environment variable for your Azure Blob Storage container name. Replace "your-container" with the actual name:

    export AZURE_CONTAINER_NAME="your-container"
#### 4.Account Key
-Store your Azure storage account key securely. You can retrieve it using the Azure CLI:

    export AZURE_ACCOUNT_KEY=$(az storage account keys list --resource-group $AZURE_RESOURCE_GROUP --account-name     
    $AZURE_STORAGE_ACCOUNT --query "[0].value" -o tsv)
#### 5.Usage in the Script
-In your clouduploader.sh script, reference these environment variables when interacting with Azure services. 

For example:

    resourceGroup="$AZURE_RESOURCE_GROUP"
    storageAccount="$AZURE_STORAGE_ACCOUNT"
    container="$AZURE_CONTAINER_NAME"
    accountKey="$AZURE_ACCOUNT_KEY"
    .
    .
    Other script logic...
## - Author
This tool was authored by GSP from the Learn to Cloud Guide.
## - Disclaimer
This tool is provided as-is, and I am not responsible for any data loss or other issues that may occur during usage. Use it at your own risk.
