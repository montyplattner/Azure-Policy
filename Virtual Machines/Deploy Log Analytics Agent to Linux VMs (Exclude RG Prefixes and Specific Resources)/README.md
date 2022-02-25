# Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)

Deploy Log Analytics extension for Linux VMs if the extension is not installed.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FVirtual%2520Machines%2FDeploy%2520Log%2520Analytics%2520Agent%2520to%2520Linux%2520VMs%2520%28Exclude%2520RG%2520Prefixes%2520and%2520Specific%2520Resources%29%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)" -DisplayName "Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)" -description "Deploy Log Analytics extension for Linux VMs if the extension is not installed." -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Log%20Analytics%20Agent%20to%20Linux%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Log%20Analytics%20Agent%20to%20Linux%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)' --display-name 'Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)' --description 'Deploy Log Analytics extension for Linux VMs if the extension is not installed.' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Log%20Analytics%20Agent%20to%20Linux%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Virtual%20Machines/Deploy%20Log%20Analytics%20Agent%20to%20Linux%20VMs%20(Exclude%20RG%20Prefixes%20and%20Specific%20Resources)/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Deploy Log Analytics extension on Linux VMs (Exclude RG Prefixes and Specific Resources)" 
````