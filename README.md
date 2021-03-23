# Create a Managed Certificate (Free) for an APEX domain (aka root/naked domain)

[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcoelho5br%2Fwebapp-bind-name-and-managed-certificate%2Fmaster%2Fcustomdomain.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fcoelho5br%2Fwebapp-bind-name-and-managed-certificate%2Fmaster%2Fcustomdomain.json)


To deploy this template, you need to have the following resources:

1. The App Service Plan (serverFarm) resource name that the Web App is running.
2. The domain should already be bound under Web App Custom Domain


This arm deployment will:

1. Create a Managed Certificate (Free).
