## Objective
Setting up a virtual machine (VM) in Azure, enrolling it into Microsoft Intune, and securing it using 
Microsoft Defender for Endpoint and other endpoint security features.

### Skills Learned
- Azure Resource Management: Understanding how to create a resource group in Azure, which is essential for organizing and managing
  resources.

- Virtual Machine (VM) Setup: Learned how to create, configure, start, stop, and manage virtual machines in Azure, including cost-saving
  practices such as shutting down VMs when not in use.

- Networking and Management in Azure: Gaining knowledge of how to configure networking settings, change shutdown times, and modify
  diagnostic settings for virtual machines in Azure.

- Remote Desktop Protocol (RDP) Usage: Learned how to connect to a virtual machine from different operating systems using RDP and
  managing access using credentials.

- Intune Enrollment: Learned how to enroll virtual machines and devices into Microsoft Intune for management and securing endpoints and set up 
 automatic enrollment for devices.

- Azure Active Directory (Entra ID) Integration: Understanding how to join devices to Azure Active Directory, confirming that a device
  is properly linked for access to corporate resources.

- Microsoft Defender for Endpoint: Gained insight into how to verify and manage the functionality of Microsoft Defender for Endpoint
  within Microsoft 365 services, including device onboarding and alert management.

- Endpoint Security Management: Mastered how to monitor and respond to alerts, vulnerabilities, and incidents related to endpoint security 
 using Microsoft 365 Defender.

- Attack Surface Reduction (ASR): Understood the principles of reducing attack surfaces and how to deploy security policies through 
 Intune and Microsoft Defender to enforce endpoint restrictions and ensure system integrity.

- Security Dashboard Navigation: Learning how to use the Microsoft Defender dashboard to view assets, track vulnerabilities, and analyze telemetry 
 data for better security insights.

### Tools Used
<div>
<img src="https://img.shields.io/badge/-Azure%20Portal-0089D6?&style=for-the-badge&logo=Microsoft%20Azure&logoColor=white" alt="Azure Portal">
<img src="https://img.shields.io/badge/-Remote%20Desktop%20Protocol-00b300?&style=for-the-badge&logo=Microsoft&logoColor=white" alt="Remote Desktop Protocol">
<img src="https://img.shields.io/badge/-Microsoft%20Intune-ff6600?&style=for-the-badge&logo=Microsoft%20Intune&logoColor=white" alt="Microsoft Intune">
<img src="https://img.shields.io/badge/-Entra%20ID%20%28Azure%20Active%20Directory%29-b300b3?&style=for-the-badge&logo=Microsoft%20Azure%20Active%20Directory&logoColor=white" alt="Entra ID (Azure Active Directory)">
<img src="https://img.shields.io/badge/-Microsoft%20365%20Defender-e60000?&style=for-the-badge&logo=Microsoft%20365&logoColor=white" alt="Microsoft 365 Defender">
<img src="https://img.shields.io/badge/-Microsoft%20Defender%20for%20Endpoint-8a8a5c?&style=for-the-badge&logo=Microsoft%20365&logoColor=white" alt="Microsoft Defender for Endpoint">
</div>

## Steps
- Create a Resource Group: All resources in Azure must be in a resource group, which acts as a container for organizing and managing those resources - 
it allows us to group related resources together for easier management, access control, and deployment e.g virtual machines. 
Next we create a new Virtual Machine; Choose the Azure subscription you want to use for the VM and the existing resource group that we created.

<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/14bba0e9806c7f38f02bb5c49bc2c78aec13e1a7/Images/creating%20virtual%20machines.png" width="300" />
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/14bba0e9806c7f38f02bb5c49bc2c78aec13e1a7/Images/Summary1.png" width="300" />
</p>

- To connect to the VM, we get the Public IP Address of the VM, Select the VM you want to connect to and under the "Overview" tab, find the Public IP address.
  Ensure RDP Port (3389) is Open in the Network Security Group (NSG). This allows us to access the VM remotely. Next we download and Open the Remote Desktop Client,
  Enter the Public IP Address, provide the credentials,that is; the username and password that you created during the VM setup. Click Connect, the RDP client will
  establish a remote desktop session to your VM, and you’ll see the Windows desktop of the VM.
  
<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/7651f3c48a68124af4c9822efeac974b1368504c/Images/Public%20Ip.png" width="300" />
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/7651f3c48a68124af4c9822efeac974b1368504c/Images/Connecting%20via%20RDP.PNG" width="335" />
</p>

- Next we enroll a device into Intune which involves installing the Company Portal app from the Microsoft Store, which facilitates the enrollment process.
  Before enrolling the VM into Intune, we first confirm that the VM is registered with Azure Active Directory(Azure AD) because Intune uses Azure AD for
  device management. Since our VM is not yet registered, we go to Settings > Accounts > Access work or school > Add a work or school account. Select Work or
  school account, then enter the credentials associated with our Azure AD account.

<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/b8c6465eaa142886ade989fc9965c265a21579c2/Images/Confirm%20your%20machine%20is%20joined.PNG" width="700" />
</p>

- We manually onboarded our device to Microsoft Defender for Endpoint using a PowerShell script. We download the Onboarding Package from Microsoft 365
  Defender portal, download and run the onboarding script using powerShell as an Administrator. The script will install the necessary sensors and
  configurations for Microsoft Defender for Endpoint.

<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/4d28dc78b5cccaf30dcf0be91064195fb370a4bf/Images/Onboarding%20using%20script.PNG" width="320" />
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/4d28dc78b5cccaf30dcf0be91064195fb370a4bf/Images/Running%20the%20onboarding%20script%20as%20Admin%20in%20cmd.PNG" width="300" />
</p>

- We can verify the status of the device to see if the onboarding was successful, Go to EndPoints > Device Inventory and ensure that all devices are
  showing up in the list with a status of "Onboarded". Once our machine is onboarded, Microsoft Defender for Endpoint will begin providing protection by
  monitoring for threats, alerts, vulnerabilities, and providing tools for incident response.

<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/5e6b2f19af461d1716d34191518c9a44eb68cf29/Images/client%20has%20been%20onboarded.PNG" width="700" />
</p>

- Onboarded devices may take some time for the service to become fully functional. For our case we are using Defender for Endpoint P1 (Plan 1) which can
  take 5-6 hours for devices to become fully protected as the device completes its onboarding and synchronization process and report into the Microsoft
  365 Defender portal.
  
<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/6f6d54a7d10f3368a55c0abab11c698db0646228/Images/No%20trial%20for%20defender%20p1.PNG" width="700" />
</p>

- Next we create a new Attack Surface Reduction (ASR) Policy in Microsoft Intune to manage and secure endpoints is an effective way to reduce the risk of
  attacks by controlling which applications and behaviors are allowed on your devices. Configure the ASR rules that are designed to reduce the attack surface.
  
<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/87b92a4b6edecd30d379b98f179b7f6182012f35/Images/Creating%20policy%20ASR.png" width="700" />
</p>

- Once our ASR policy is configured, we'll assign it to the relevant device groups in Intune. We choose which groups or devices we want the policy to apply to.
  After assigning the policy to the desired groups, click on Create or Save to deploy the ASR policy. The policy will then be pushed out to the assigned devices, and the settings will take effect on those endpoints.

<p align="center">
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/086806a6f67daedc0e9f569fd883d3761676dee6/Images/ASR%20policy%20created.png" width="300" />
  <img src="https://github.com/NgethaWachira/Microsoft-Virtual-machine/blob/086806a6f67daedc0e9f569fd883d3761676dee6/Images/this%20is%20where%20it%20will%20show%20if%20it%20deployed%20successfully.PNG" width="318" />
</p>





