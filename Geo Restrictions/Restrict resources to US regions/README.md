# Allowed locations

This policy enables you to restrict the locations your organization can specify when deploying resources. Use to enforce your geo-compliance requirements. Excludes resource groups, Microsoft.AzureActiveDirectory/b2cDirectories, and resources that use the 'global' region.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FGeo%2520Restrictions%2FRestrict%2520resources%2520to%2520US%2520regions%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "allowed-locations-resources" -DisplayName "Allowed locations" -description "This policy enables you to restrict the locations your organization can specify when deploying resources. Use to enforce your geo-compliance requirements. Excludes resource groups, Microsoft.AzureActiveDirectory/b2cDirectories, and resources that use the 'global' region" -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resources%20to%20US%20regions/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resources%20to%20US%20regions/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'allowed-locations-resources' --display-name 'Allowed locations' --description 'This policy enables you to restrict the locations your organization can specify when deploying resources. Use to enforce your geo-compliance requirements. Excludes resource groups, Microsoft.AzureActiveDirectory/b2cDirectories, and resources that use the 'global' region' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resources%20to%20US%20regions/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Geo%20Restrictions/Restrict%20resources%20to%20US%20regions/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "allowed-locations-resources" 

````

## Acknowledgments
* [Azure Polcy - AllowedLocations_Deny](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/General/AllowedLocations_Deny.json)