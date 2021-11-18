# Allowed VM SKUs for Windows Based Images

This policy restricts the VM Size SKUs that can be used when deploying a Windows based image.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FVirtual%2520Machines%2FAllowed%2520VM%2520SKUs%2520for%2520Windows%2520based%2520Images%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Allowed VM SKUs for Windows Based Images" -DisplayName "Allowed VM SKUs for Windows Based Images" -description "This policy restricts the VM Size SKUs that can be used when deploying a Windows based image" -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Allowed%20VM%20SKUs%20for%20Windows%20based%20Images/azurepolicy.parameters.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Allowed%20VM%20SKUs%20for%20Windows%20based%20Images/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'Allowed VM SKUs for Windows Based Images' --display-name 'Allowed VM SKUs for Windows Based Images' --description 'This policy restricts the VM Size SKUs that can be used when deploying a Windows based image' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Allowed%20VM%20SKUs%20for%20Windows%20based%20Images/azurepolicy.parameters.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Allowed%20VM%20SKUs%20for%20Windows%20based%20Images/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Allowed VM SKUs for Windows Based Images" 

````