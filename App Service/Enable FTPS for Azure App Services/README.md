# Enable FTPS for Azure App Services

This policy automatically enables FTPS for Azure App Services (Web App and Function App).

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FApp%2520Service%2FEnable%2520FTPS%2520for%2520Azure%2520App%2520Services%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "app-services-enable-ftps" -DisplayName "Enable FTPS for Azure App Services" -description "This policy automatically enables FTPS for Azure App Services (Web App and Function App)" -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20FTPS%20for%20Azure%20App%20Services/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20FTPS%20for%20Azure%20App%20Services/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'app-services-enable-ftps' --display-name 'Enable FTPS for Azure App Services' --description 'This policy automatically enables FTPS for Azure App Services (Web App and Function App)' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20FTPS%20for%20Azure%20App%20Services/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/App%20Service/Enable%20FTPS%20for%20Azure%20App%20Services/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "app-services-enable-ftps" 

````

## Acknowledgments
* [Enable FTPS on Azure App Services with Azure Policy](https://charbelnemnom.com/enable-ftps-on-azure-app-services-with-azure-policy/)