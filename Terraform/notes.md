- Azure: Uses ARM templates for infrastructure as code.
- AWS: Uses CloudFormation templates for infrastructure as code.
- Google Cloud Platform: Uses Deployment Manager and Deployment Manager templates for infrastructure as code😊

Why do people use Terraform if Iac tools already exists in Cloud Providers🙄?

while cloud providers offer their own tools for managing infrastructure as code

      Terraform is ability to work with multiple cloud providers and other infrastructure platforms.
      with terraform you can manage resources across AWS, GCP, Azure as well as on-premises environments, all using a 
      single configuration language and workflow.
      
      consistent work flow for managing infrastucture across different workflows and environments. this means you can use the same commands
      and workflows regardless of underlying infrastucture, which simplifies management process.
      
      State Management - Terraform maintains a state file that keeps track of the resources it manages and their current state. 
      This state file helps Terraform understand the relationships between resources and manage updates, dependencies, and drift detection more effectively.
      It also provides features like resource locking to prevent concurrent modifications and state versioning for collaboration and auditing purposes.


```
resource "azurerm_resource_group" "example" {
  name     = "example-resources"
  location = "West Europe"
}

resource - keyword in terraform refers to resource block
"azurerm_resource_group" - Resource type, specifically targetted resource group
"example" - local name given to the resource block
name - name of the azure resource you want to create
```
```
# Define Azure Provider [ mandatory field to create resources ]
provider "azurerm" {
  features {}         
}
```

>✅ mandatory resorces that vm create along with it's creation
      - Public Ip adress  
      - Disk  
      - Network Interface  
      - Network Security Group
      - Virtual Network

variables - Input and output variables in Terraform are essential for parameterizing and sharing values within your Terraform configurations and modules.   
They allow you to make your configurations more dynamic, reusable, and flexible.  
      input variables - allows you to pass the values  
      output variables - allows you to print the variables  
# Creating a Resource Group using Variables
```
variable "resource_group_name" {
    description = "resource group name"  
}
variable "location" {
    description = "location"
  
}
provider "azurerm" {
    features {}
    
}
resource "azurerm_resource_group" "local-rg" {
    name = var.resource_group_name
    location = var.location
}
```
# Creating a Resource Group using terraform.tfvars file  
```
#main.tf
provider "azurerm" {
      features{}
}
variable "rg_name" {}
variable "loc" {}
resource "azurerm_resource_group" "local-rg" {
      name = var.rg-name
      location = var.loc
}
```
```
# terraform.tfvars
rg_name = "sreelakshmi-rg"
loc = "east us"
```
terraform plan -var-file="<name> .tfvars"--> if we are gave different name for .tfvar file instead of terraform.tfvar   

# Create a Resource group and Print subscription Id of that resource group is created [ outputs.tf ]
```
# main.tf
provider "azurerm" {
        features{}
}
variable "rg_name" {}
variable "loc" {}
resource "azurerm_resource_group" "local-rg"{
        name = var.rg_name
        location = var.loc
}
data "azurerm_subscription" "current" {}
```
```
# outputs.tf
output "sub_id" {
  value=data.azurerm_subscription.current.subscription_id
}
```

whenever we are writting modules we no need to create variables.tfvar file





