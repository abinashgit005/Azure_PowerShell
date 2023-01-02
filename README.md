https://learn.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-9.2.0

# Azure PowerShell
## ExecutionPolicy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser


## installation
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force


## Connect-AzAccount
![azconnect](required Images/azconnect.png)

 

## Creating a resource group 
![resource Group](required Images/resourcegrp.png)
 


output as below:
![output](required Images/output.png)

help cmdlet for new resource group 
![get-help command](required Images/gethelp.png)
 

## We can create application object to avail a non-interactive login.
1. Go to azure active directory.
2. App registration > new App registration > mention appropriate name > create
3. you can see Application ID, Object ID, Tenant ID


