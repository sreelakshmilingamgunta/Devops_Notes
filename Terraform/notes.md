- Azure: Uses ARM templates for infrastructure as code.
- AWS: Uses CloudFormation templates for infrastructure as code.
- Google Cloud Platform: Uses Deployment Manager and Deployment Manager templates for infrastructure as code😊

Why do people use Terraform if Iac tools already exists in Cloud Providers?

while cloud providers offer their own tools for managing infrastructure as code

      Terraform is ability to work with multiple cloud providers and other infrastructure platforms.
      with terraform you can manage resources across AWS, GCP, Azure as well as on-premises environments, all using a 
      single configuration language and workflow.
      
      consistent work flow for managing infrastucture across different workflows and environments. this means you can use the same commands
      and workflows regardless of underlying infrastucture, which simplifies management process.
      
      State Management - Terraform maintains a state file that keeps track of the resources it manages and their current state. 
      This state file helps Terraform understand the relationships between resources and manage updates, dependencies, and drift detection more effectively.
      It also provides features like resource locking to prevent concurrent modifications and state versioning for collaboration and auditing purposes.


- resource "azurerm_resource_group" "example" {
  name     = "example-resources"
  location = "West Europe"
}
resource - keyword in terraform refers to resource block
"azurerm_resource_group" - Resource type, specifically targetted resource group
"example" - local name given to the resource block
name - name of the azure resource you want to create

