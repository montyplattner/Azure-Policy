# Allowed locations for resource groups

This policy enables you to restrict the locations your organization can create resource groups in. Use to enforce your geo-compliance requirements..

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FGeo%2520Restrictions%2FRestrict%2520resource%2520groups%2520to%2520US%2520regions%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Allowed locations for resource groups" -DisplayName "Allowed locations for resource groups" -description "This policy enables you to restrict the locations your organization can create resource groups in. Use to enforce your geo-compliance requirements." -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resource%20groups%20to%20US%20regions/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resource%20groups%20to%20US%20regions/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'Allowed locations for resource groups' --display-name 'Allowed locations for resource groups' --description 'This policy enables you to restrict the locations your organization can create resource groups in. Use to enforce your geo-compliance requirements.' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resource%20groups%20to%20US%20regions/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resource%20groups%20to%20US%20regions/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Allowed locations for resource groups" 

````

## Acknowledgments
* [Azure Polcy - ResourceGroupAllowedLocations_Deny](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/General/ResourceGroupAllowedLocations_Deny.json)