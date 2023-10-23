# Challenge 7 - PowerShell Cloud
## Introduction
The following from [Azure PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/azure/?view=azps-9.2.0):
>Azure PowerShell is a set of cmdlets for managing Azure resources directly from PowerShell. Azure PowerShell is designed to make it easy to learn and get started with, but provides powerful features for automation.

Let's learn about Azure PowerShell!

## Challenge A - Create a VM in Azure
In this challenge you have to write a PowerShell script that will create a VM in Azure. Here are the requirements:\
_Note: the requirements are not necessarily in order - read all the requirements before starting.  Perhaps rearrange them as opening comments in your script file to something that makes sense to you. If there's something you can't seem to get right, skip it and go on to the next item - the answer may reveal itself as you proceed..._
- The Az module is required for this script.  The script should check if the module is installed, if not it should install it.  
- Complete script help should be available.
- Specify the tenantId and subscriptionId of the customer as parameters.
    - Connect to the appropriate customer subscription using modern authentication.\
    _**Important: Do not use an actual customer subscription for this - use your own lab subscription.**_
    - These parameters should be mandatory and validated.
- Specify the customer name as a mandatory parameter.
    - Use the customer name as part of the name of the new resource group to be created for the VM.  The resource group should use the following naming convention: "[Customer Name]-psStudy-rg".
    - The name of the VM should similarly be created as "[Customer Name]-psStudy-vm".
- All resources should be created in the South Africa North region.
- Image: Ubuntu Server 20.04 LTS.
- Size: Standard D2s v3.
- Authentication: Password.
    - The script should create a random strong password that satisfies the password requirement.
    - The username and password should be written to the terminal along with a message that the password will not be saved anywhere else.
    - The script should clean up and variables that contain the password at the end of execution.
    - Obviously, don't write the password to the log file.  But writing the username to the log file will be useful.  Also, make this part of the feedback message after the script finished. 
- VNET: Create a new VNET and subnet with default parameters.
- Public IP: The VM should have a static public IP assigned.
    - The Public IP assigned should be written to the log file and like with the password above, should be written to the terminal as feedback to the user that ran the script.
- Inbound port rules: The script should read your public IP and create an NSG rule to allow only your public IP access to the VM over SSH.\
_Hint: Perhaps you created a function in a previous challenge that would help with this..._
- Any requirements not specified is left to your discretion, but keep required runtime parameters to a minimum. 
- The script should have error handling and create a log file as per previous challenges.

**_Important! Do not hardcode any credentials, TenantIds, or SubscriptionIds in your script - use parameters to obtain these at runtime.  Remember that we want to merge your work back into a public repo afterwards._**

- Open Terminal and SSH to the VM your script created to verify that the VM actually works as intended. 
- Use PowerShell commands to clean up everything your script created.\
_Hint: Delete the resource group that contains the VM and related resources you created._

## Challenge B - Azure Survey
Similar to the previous challenge, you are going to create a PowerShell script that will connect to a customer's Azure environment - this time to perform a survey.

_**Important: Do not use an actual customer subscription for this - use your own lab subscription.**_


If you had been given the task to review a customer's Azure environment, after getting credentials, what would be the things you look for? Here are a few examples to get you started:
- Resource list and important details like resource types, resource groups, and locations.
- Security:
    - Secure Score percentage.
    - Microsoft Defender for Cloud activation.
    - Summary of current outstanding alerts, including number of alerts per severity and age.\
    _Tip: If your subscription doesn't have any active alerts, try creating sample alerts from the portal._
    - Number of active recommendations.
- Networking:
    - List public IPs.
- Check out the [Azure PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/azure/what-is-azure-powershell?view=azps-9.2.0) to see if there are other interesting pieces of information you can gather about the Azure environment.

As with the previous challenge, make sure to include the following features in your script:
- _**Important: Do not use an actual customer subscription for this - use your own lab subscription.**_
- **_Important! Do not hardcode any credentials, TenantIds, or SubscriptionIds in your script - use parameters to obtain these at runtime.  Remember that we want to merge your work back into a public repo afterwards._**
- Checking if the Az module is installed.
- Use parameters to get connection information (TenantId and SubscriptionId).
- Use error handing and produce a logfile.
- Use internal functions where it makes sense.
- Export the survey results to a file.
    - Extra credit: export to JSON or CSV.  Then import the file into Excel for further analysis.  

## Challenge C - Emergency Access Accounts via the MS Graph
Create a script that will create emergency access accounts in an Azure AD tenant.

_**Important: Do not use an actual customer subscription for this - use your own lab subscription.**_

The following from [Microsoft Graph PowerShell overview](https://learn.microsoft.com/en-us/powershell/microsoftgraph/overview?view=graph-powershell-1.0)
>The Microsoft Graph PowerShell SDK acts as an API wrapper for the Microsoft Graph APIs, exposing the entire API set for use in PowerShell. It contains a set of cmdlets that helps you manage identities at scale from automating tasks to managing users in bulk using Azure Active Directory (Azure AD). It will help administer every Azure AD feature that has an API in Microsoft Graph.

Also, this note from [Manage emergency access accounts in Microsoft Entra ID](https://learn.microsoft.com/en-us/azure/active-directory/roles/security-emergency-access)
>It is important that you prevent being accidentally locked out of your Microsoft Entra organization because you can't sign in or activate another user's account as an administrator. You can mitigate the impact of accidental lack of administrative access by creating two or more _emergency access accounts_ in your organization.

Create a PowerShell script that will create emergency access accounts using the MS Graph PowerShell SDK.  Your script should feature the following:
- _**Important: Do not use an actual customer subscription for this - use your own lab subscription.**_
- **_Important! Do not hardcode any credentials, TenantIds, or SubscriptionIds in your script - use parameters to obtain these at runtime.  Remember that we want to merge your work back into a public repo afterwards._**
- Import the appropriate Microsoft.Graph modules. Microsoft.Graph has several large modules and the script will be very slow if you import all of the modules. Figure out which ones you need for your script to work.
- Connecting to the Graph should be done interactively every time the script is used. Note: once the Graph is authorised, running the script again will use the same credentials as in the previous session. The script should avoid this somehow.
- The script should generate a random strong password for each of the EAAs. It should obviously display the generated password as output of the script.
- The script should respond to the `Get-Help` cmdlet.
- The script should have proper error handling.

### Extra Credit
Create two scripts that will create an 'MFA Exclude' security group in Entra ID for use in conditional access exclusions.  One must exclude emergency access accounts from MFA in Conditional access.
- Script one will read and export users from Entra ID.  You manually edit this file to indicate which users to be added to the group.
- The second script will read the modified file and add the selected users to the 'MFA Exclude' group.
- Do all the usual things like error handling, parameters, and script help.