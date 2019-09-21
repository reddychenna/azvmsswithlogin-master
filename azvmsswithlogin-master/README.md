# azvmsswithlogin
Terraform project with login. 
To use this code, you need to export the required variable in the .bash_profile of the machine from where you want to execute this code.

----------------------------Steps to login to Auzre through terrafrom -----------------

1. Create a Service profile after you login to azure with with 'az login' command'
          az ad sp create-for-rbac --name ServicePrincipalName
2. Above command would give you output like:
          {
  "appId": "11111111-0000-0000-0000-000000000000",
  "displayName": "azure-cli-2017-06-05-10-41-15",
  "name": "http://azure-cli-2017-06-05-10-41-15",
  "password": "ASDF-0000-0000-0000-000000000000",
  "tenant": "22222222-0000-0000-0000-000000000000"
  }
 These values map to the Terraform variables like so:
    appId is the client_id defined above.
    password is the client_secret defined above.
    tenant is the tenant_id defined above.
3. Get your subscription id from Azure protal. Then Reaplce the ARM_SUBSCRIPTION_ID with that. Other Three listed below 
   will be repalced with the value you get from Step #2.  Add these four export statements to your .bash_profile
   export ARM_CLIENT_ID="11111111-0000-0000-0000-000000000000"
   export ARM_CLIENT_SECRET="ASDF-0000-0000-0000-000000000000"
   export ARM_SUBSCRIPTION_ID="00000000-0000-0000-0000-000000000000"
   export ARM_TENANT_ID="22222222-0000-0000-0000-000000000000"
4. source ~/.bash_profile  
After this step all the credentails needed to login in to AUZRE with Terraform are avaiable. You can execute any terraform plan now.

