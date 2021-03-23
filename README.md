# Create a Managed Certificate (Free) for an APEX domain (aka root/naked domain)

[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcoelho5br%2FCreate-managed-certificate-for-APEX-Domain%2Fmaster%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fcoelho5br%2FCreate-managed-certificate-for-APEX-Domain%2Fmaster%2Fazuredeploy.json)


To deploy this template, you need to have the following resources:

1. The App Service Plan (serverFarm) resource name that the Web App is running.
2. The domain should already be bound under Web App Custom Domain


This arm deployment will:

1. Create a Managed Certificate (Free).

The operation is expected to take some time.


You can also deploy using the powershell:

````
#Connect-AzureRmAccount

$subscription = "XXXXX-XXXX-XXX-XXXX-XXXXXXX"
$resourceGroupName = "MyResourceGroupwheretheASPislocated"
$appServicePlanName = "ASP-TEST-CERT"
$subjectName = "contoso.com"

Set-AzureRmContext -SubscriptionId $subscription

$appServicePlan = Get-AzureRmResource `
    | Where-Object {$_.ResourceGroupName -eq $resourceGroupName } `
    | Where-Object {$_.Name -eq $appServicePlanName}

New-AzureRMResourceGroupDeployment `
    -ResourceGroupName $resourceGroupName `
    -SubjectName $subjectName `
    -AppServicePlanName $appServicePlanName `
    -Location $appServicePlan.Location `
    -TemplateFile "CreateHttpFreeCert.json" 
````