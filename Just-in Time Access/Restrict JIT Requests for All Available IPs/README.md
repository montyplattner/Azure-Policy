# Restrict JIT Requests for All Available IPS

This policy restricts the ability to select 'All Available IPs' when making a Just-in Time request to a VMs.

## Deploy using the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmontyplattner%2FAzure-Policy%2Fmain%2FJust-in%2520Time%2520Access%2FRestrict%2520JIT%2520Requests%2520for%2520All%2520Available%2520IPs%2Fazurepolicy.json)

## Deploy using Azure PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "Restrict JIT Requests for All Available IPS" -DisplayName "Restrict JIT Requests for All Available IPS" -description "This policy restricts the ability to select 'All Available IPs' when making a Just-in Time request to a VMs." -Policy 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Just-in%20Time%20Access/Restrict%20JIT%20Requests%20for%20All%20Available%20IPs/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Just-in%20Time%20Access/Restrict%20JIT%20Requests%20for%20All%20Available%20IPs/azurepolicy.parameters.json' -Mode All

$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -PolicyDefinition $definition

$assignment 
````

## Deploy using Azure CLI

````cli

az policy definition create --name 'Restrict JIT Requests for All Available IPS' --display-name 'Restrict JIT Requests for All Available IPS' --description 'This policy restricts the ability to select 'All Available IPs' when making a Just-in Time request to a VMs.' --rules 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Just-in%20Time%20Access/Restrict%20JIT%20Requests%20for%20All%20Available%20IPs/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/montyplattner/Azure-Policy/main/Just-in%20Time%20Access/Restrict%20JIT%20Requests%20for%20All%20Available%20IPs/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "Restrict JIT Requests for All Available IPS" 

````

## Acknowledgments
* [deny-wildcard-source-for-just-in-time-requests](https://github.com/bonJoeV/azure-policy/blob/main/deny-wildcard-source-for-just-in-time-requests/README.md)