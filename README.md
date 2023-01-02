# Azure PowerShell
## Reference link : 
https://learn.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-9.2.0
## ExecutionPolicy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser


## installation
```PowerShell
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```

## Connect-AzAccount
```PowerShell
Connect-AzAccount
```
![azconnect](connect.png)

 

## Creating a resource group 
```Powershell
$ResourceGroup = "Powershell-grp"
$Location = "Central India"
New-AzResourceGroup -Name $ResourceGroup -Location $Location
```
![resource Group](resourcegroup.png)
 


output as below:
![output](output.png)

help cmdlet for new resource group 
```PowerShell
Get-Help New-AzResourceGroup -full
```
![get-help command](gethelp.png)
 

## We can create application object to avail a non-interactive login.
1. Go to azure active directory.
2. App registration > new App registration > mention appropriate name > create
3. you can see Application ID, Object ID, Tenant ID


