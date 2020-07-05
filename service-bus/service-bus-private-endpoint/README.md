# Service Bus namespaces should use private links

Audit Service Bus namespaces that do not have at least one approved private endpoint connection. Clients in a virtual network can securely access resources that have private endpoint connections through private links. For more information, visit: https://aka.ms/acr/private-link

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdavidokeyode%2Fcharis-cloud-azure-policy%2Fmaster%2Fservice-bus%2Fservice-bus-private-endpoint%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "service-bus-private-endpoint" -DisplayName "Service Bus namespaces should use private links" -description "Audit Service Bus namespaces that do not have at least one approved private endpoint connection. Clients in a virtual network can securely access resources that have private endpoint connections through private links. For more information, visit: https://aka.ms/acr/private-link" -Policy 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-private-endpoint/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-private-endpoint/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'service-bus-private-endpoint' --display-name 'Service Bus namespaces should use private links' --description 'Audit Service Bus namespaces that do not have at least one approved private endpoint connection. Clients in a virtual network can securely access resources that have private endpoint connections through private links. For more information, visit: https://aka.ms/acr/private-link' --rules 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-private-endpoint/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-private-endpoint/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "service-bus-private-endpoint" 