# Service bus namespaces should have firewall rules

Audit or deny Service bus namespaces that do not have any IP rules configured and allow all networks by default. Namespaces that have at least one IP rule defined with the virtual network filter enabled are deemed compliant. Namespaces disabling public access are also deemed compliant.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdavidokeyode%2Fcharis-cloud-azure-policy%2Fmaster%2Fservice-bus%2Fservice-bus-firewall%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "service-bus-firewall" -DisplayName "Service bus namespaces should have firewall rules" -description "Audit or deny Service bus namespaces that do not have any IP rules configured and allow all networks by default. Namespaces that have at least one IP rule defined with the virtual network filter enabled are deemed compliant. Namespaces disabling public access are also deemed compliant" -Policy 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-firewall/azurepolicy.json' -Parameter 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-firewall/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'service-bus-firewall' --display-name 'Service bus namespaces should have firewall rules' --description 'Audit or deny Service bus namespaces that do not have any IP rules configured and allow all networks by default. Namespaces that have at least one IP rule defined with the virtual network filter enabled are deemed compliant. Namespaces disabling public access are also deemed compliant' --rules 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-firewall/azurepolicy.json' --params 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-firewall/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "service-bus-firewall" 