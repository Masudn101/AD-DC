Below is a PowerShell script to create a new forest and domain controller in Active Directory:

```powershell
# Define parameters for forest and domain
$ForestName = "example.com"
$DomainName = "example"
$SafeModeAdministratorPassword = ConvertTo-SecureString "P@ssw0rd123!" -AsPlainText -Force

# Install Active Directory Domain Services feature
Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools

# Promote server to domain controller
Install-ADDSForest -DomainName $DomainName -DomainMode "Win2016" -ForestMode "Win2016" `
    -SafeModeAdministratorPassword $SafeModeAdministratorPassword -Force:$true
```

This script defines parameters such as the forest name, domain name, and the password for the Directory Services Restore Mode (DSRM) administrator account. Then it installs the Active Directory Domain Services feature and promotes the server to a domain controller with the specified domain and forest modes.

Make sure to replace the placeholders (`$ForestName`, `$DomainName`, and `$SafeModeAdministratorPassword`) with your actual values.

Save the script with a `.ps1` extension and execute it on your Windows Server with appropriate administrative privileges. Make sure to adjust the forest and domain modes according to your requirements.
