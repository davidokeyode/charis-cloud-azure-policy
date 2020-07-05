# Ensure storage accounts should not allow public Blobs

Storage accounts should not allow public Blobs

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdavidokeyode%2Fcharis-cloud-azure-policy%2Fmaster%2Fstorage%2Fstorage-account-public-blob%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "storage-account-public-blob" -DisplayName "Storage accounts should not allow public Blobs" -description "Ensure storage accounts should not allow public Blobs" -Policy 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/storage/storage-account-public-blob/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/storage/storage-account-public-blob/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'storage-account-public-blob' --display-name 'Storage accounts should not allow public Blobs' --description 'Ensure storage accounts should not allow public Blobs' --rules 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/storage/storage-account-public-blob/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/storage/storage-account-public-blob/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "storage-account-file-encryption" 