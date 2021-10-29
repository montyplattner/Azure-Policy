# Enable HTTPS for Azure Web Apps

This policy automatically enables HTTPS for new Azure App Services (Web App and Function App) deployments.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FApp%2520Service%2FEnable%2520HTTPS%2520for%2520Azure%2520App%2520Services%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Enable HTTPS for Azure Web Apps" -DisplayName "Enable HTTPS for Azure Web Apps" -description "This policy automatically enables HTTPS for new Azure App Services (Web App and Function App) deployments" -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20HTTPS%20for%20Azure%20App%20Services/azurepolicy.rules.json?token=AMCM2OLIJFDDN4BNPGLQBKLBPQJ5Q' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20HTTPS%20for%20Azure%20App%20Services/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````



## Deploy using Azure CLI

````cli

az policy definition create --name 'Enable HTTPS for Azure Web Apps' --display-name 'Enable HTTPS for Azure Web Apps' --description 'This policy automatically enables HTTPS for new Azure App Services (Web App and Function App) deployments' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20HTTPS%20for%20Azure%20App%20Services/azurepolicy.rules.json?token=AMCM2OLIJFDDN4BNPGLQBKLBPQJ5Q' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20HTTPS%20for%20Azure%20App%20Services/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Enable HTTPS for Azure Web Apps" 

````

## Acknowledgments
* [Enable HTTPS on Azure App Services With Azure Policy](https://charbelnemnom.com/enable-https-on-azure-app-services-with-azure-policy/)