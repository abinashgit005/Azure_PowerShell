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
 
We can not run Connect-AZAccount evry time. Instead of that we can create Application Object to access it.

## We can create application object to avail a non-interactive login.
1. Go to azure active directory.
2. App registration > new App registration > mention appropriate name > create
3. you can see Application ID, Object ID, Tenant ID
4. Add contributor role the the service principal.

```PowerShell
$ResourceGroup = "Powershell-grp"
$Location = "Central India"
$AppID = "5181d082-2ba5-4a01-bd94-XXXXXXXX"
$TenantID = "df77f402-7f2e-47d2-bea6-XXXXXXXXXXXXX"
$AppSecret = "BZ28Q~m02QX12ABvPYFzYESE556.UZXXXXXXXXXX"
$scuresecret = $AppSecret | ConvertTo-SecureString -AsPlainText -Force
$Credential = New-Object -TypeName  System.Management.Automation.PSCredential -ArgumentList $AppID,$scuresecret

Connect-AzAccount -ServicePrincipal -Credential $Credential -Tenant $TenantID

New-AzResourceGroup -Name $ResourceGroup -Location $Location
```

This will Automatically use the credentials and create desired resource for us.

## List out all the ResourceGroup in your Subscription with status.

```PowerShell
$RGlist=Get-AzResourceGroup
$RGlist #Printing the RGList just for cross checking.
foreach($group in $RGlist)
{
    "Provisioning state is : " + $group.ProvisioningState
}
```
## StorageAccount
![Reference Link](/https://learn.microsoft.com/en-us/powershell/module/az.storage/new-azstorageaccount?view=azps-9.2.0)