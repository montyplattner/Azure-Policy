# [POLICY NAME]

[POLICY DESCRIPTION].

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/[GITHUB URL ENCODED azurepolicy.json])

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "[POLICY NAME]" -DisplayName "[POLICY NAME]" -description "[POLICY DESCRIPTION]" -Policy '[GITHUB URL azurepolicy.parameters.json]' -Parameter '[GITHUB URL azurepolicy.parameters.json]' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name '[POLICY NAME]' --display-name '[POLICY NAME]' --description '[POLICY DESCRIPTION]' --rules '[GITHUB URL azurepolicy.parameters.json]' --params '[GITHUB URL azurepolicy.parameters.json]' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "[POLICY NAME]" 

````

## Acknowledgments
* [Article Title](Link to Article)