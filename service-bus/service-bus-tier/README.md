# Service Bus namespaces should use the premium tier

Service Bus namespaces should use the premium tier

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdavidokeyode%2Fcharis-cloud-azure-policy%2Fmaster%2Fservice-bus%2Fservice-bus-tier%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "service-bus-tier" -DisplayName "Service Bus namespaces should use the premium tier" -description "Service Bus namespaces should use the premium tier" -Policy 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-tier/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-tier/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'service-bus-tier' --display-name 'Service Bus namespaces should use the premium tier' --description 'Service Bus namespaces should use the premium tier' --rules 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-tier/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/davidokeyode/charis-cloud-azure-policy/master/service-bus/service-bus-tier/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "service-bus-tier" 