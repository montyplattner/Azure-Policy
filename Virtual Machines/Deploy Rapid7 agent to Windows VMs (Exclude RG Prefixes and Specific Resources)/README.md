# Deploy Rapid7 agent to Windows VMs (Exclude RG Prefixes and Specific Resources)

Deploy Rapid7 extension for Windows VMs if the extension is not installed.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fgithub.com%2Fmontyplattner%2FAzure-Policy%2Fblob%2Fmain%2FVirtual%2520Machines%2FDeploy%2520Rapid7%2520agent%2520to%2520Windows%2520VMs%2520%28Exclude%2520RG%2520Prefixes%2520and%2520Specific%2520Resources%29%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Deploy Rapid7 agent to Windows VMs (Exclude RG Prefixes and Specific Resources)" -DisplayName "Deploy Rapid7 agent to Windows VMs" -description "Deploy Rapid7 extension for Windows VMs if the extension is not installed." -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Rapid7%20agent%20to%20Windows%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Rapid7%20agent%20to%20Windows%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'Deploy Rapid7 agent to Windows VMs (Exclude RG Prefixes and Specific Resources)' --display-name 'Deploy Rapid7 agent to Windows VMs' --description 'Deploy Rapid7 extension for Windows VMs if the extension is not installed.' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Rapid7%20agent%20to%20Windows%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Rapid7%20agent%20to%20Windows%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Deploy Rapid7 agent to Windows VMs" 

````