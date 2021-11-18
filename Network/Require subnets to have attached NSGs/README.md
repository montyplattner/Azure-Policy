# Require subnets to have attached NSGs

This policy requires all subnets to have an associated NSG attached to them.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FNetwork%2FRequire%2520subnets%2520to%2520have%2520attached%2520NSGs%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "require-subnet-NSG" -DisplayName "Require subnets to have attached NSGs" -description "This policy requires all subnets to have an associated NSG attached to them" -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Network/Require%20subnets%20to%20have%20attached%20NSGs/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Network/Require%20subnets%20to%20have%20attached%20NSGs/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition

$assignment 
````



## Deploy using Azure CLI

````cli

az policy definition create --name 'require-subnet-NSG' --display-name 'Require subnets to have attached NSGs' --description 'This policy requires all subnets to have an associated NSG attached to them' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Network/Require%20subnets%20to%20have%20attached%20NSGs/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Network/Require%20subnets%20to%20have%20attached%20NSGs/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "require-subnet-NSG" 

````

## Acknowledgments
* [Azure Community Policy Github - Prevent subnets without NSG](https://github.com/Azure/Community-Policy/tree/master/Policies/Network/Prevent%20subnets%20without%20NSG)
* [Azure Policy Github - enforce-nsg-on-subnet](https://github.com/Azure/azure-policy/tree/master/samples/Network/enforce-nsg-on-subnet)