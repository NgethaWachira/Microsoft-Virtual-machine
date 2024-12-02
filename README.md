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
Create a Resource Group: All resources in Azure must be in a resource group, which acts as a container for organizing and managing those resources - 
it allows us to group related resources together for easier management, access control, and deployment e.g virtual machines. 
Next we create a new Virtual Machine; Choose the Azure subscription you want to use for the VM and the existing resource group that we created.

<p align="center">
  <img src="https://github.com/NgethaWachira/Virtual-Malware-Analysis-Lab/blob/a0f3edadb0f52cdf430d36ad88db3f38ce9d3637/Images/IPv4%20settings%20Windows.PNG" width="300" />
  <img src="https://github.com/NgethaWachira/Virtual-Malware-Analysis-Lab/blob/f27b3135ec321a5615146d69352d69ed2679493e/Images/IPv4%20settings%20Kali.PNG" width="300" />
</p>


