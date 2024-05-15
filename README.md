# AD-DC



```
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
