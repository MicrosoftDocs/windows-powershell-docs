---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.2.0
Locale: en-US
Module Guid: 81d5df9c-8fe3-46d7-a9bf-2aedd60d1843
Module Name: RemoteDesktop
ms.date: 12/20/2016
title: RemoteDesktop
---

# RemoteDesktop Module
## Description
This reference provides cmdlet descriptions and syntax for all Remote Desktop Service-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## RemoteDesktop Cmdlets
### [Add-RDServer](./Add-RDServer.md)
Adds an RDS server to a Remote Desktop deployment.

### [Add-RDSessionHost](./Add-RDSessionHost.md)
Adds one or more RD Session Host servers to a session collection.

### [Add-RDVirtualDesktopToCollection](./Add-RDVirtualDesktopToCollection.md)
Adds virtual desktops to a virtual desktop collection.

### [Disable-RDVirtualDesktopADMachineAccountReuse](./Disable-RDVirtualDesktopADMachineAccountReuse.md)
Prevents the RD Connection Broker server from reusing existing Active Directory (AD) computer accounts.

### [Disconnect-RDUser](./Disconnect-RDUser.md)
Disconnects a user from a session that runs on a remote server.

### [Enable-RDVirtualDesktopADMachineAccountReuse](./Enable-RDVirtualDesktopADMachineAccountReuse.md)
Configures the RD Connection Broker server to reuse existing AD DS computer accounts.

### [Export-RDPersonalSessionDesktopAssignment](./Export-RDPersonalSessionDesktopAssignment.md)
Exports the current map of personal session desktops to users.

### [Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)
Exports the current associations between users and personal virtual desktops to a file.

### [Get-RDAvailableApp](./Get-RDAvailableApp.md)
Gets a list of publishable applications from a collection.

### [Get-RDCertificate](./Get-RDCertificate.md)
Gets certificates associated with RDS roles.

### [Get-RDConnectionBrokerHighAvailability](./Get-RDConnectionBrokerHighAvailability.md)
Gets high availability settings for the RD Connection Broker server in a Remote Desktop deployment.

### [Get-RDDeploymentGatewayConfiguration](./Get-RDDeploymentGatewayConfiguration.md)
Gets configuration settings for the RD Gateway for a Remote Desktop deployment.

### [Get-RDFileTypeAssociation](./Get-RDFileTypeAssociation.md)
Displays the file extensions associated with a RemoteApp program.

### [Get-RDLicenseConfiguration](./Get-RDLicenseConfiguration.md)
Retrieves the current settings for the RD Licensing server and the licensing mode of the Remote Desktop deployment.

### [Get-RDPersonalSessionDesktopAssignment](./Get-RDPersonalSessionDesktopAssignment.md)
Gets personal session desktop assignments.

### [Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)
Retrieves a list of personal virtual desktops and associated user accounts.

### [Get-RDPersonalVirtualDesktopPatchSchedule](./Get-RDPersonalVirtualDesktopPatchSchedule.md)
Gets a patch schedule for a virtual desktop.

### [Get-RDRemoteApp](./Get-RDRemoteApp.md)
Gets RemoteApp programs in a Remote Desktop deployment.

### [Get-RDRemoteDesktop](./Get-RDRemoteDesktop.md)
Gets published Remote Desktop connections.

### [Get-RDServer](./Get-RDServer.md)
Gets RDS servers in a Remote Desktop deployment.

### [Get-RDSessionCollection](./Get-RDSessionCollection.md)
Gets session collections in a Remote Desktop deployment.

### [Get-RDSessionCollectionConfiguration](./Get-RDSessionCollectionConfiguration.md)
Gets configuration information for a session collection.

### [Get-RDSessionHost](./Get-RDSessionHost.md)
Gets a list of RD Session Host servers in a session collection.

### [Get-RDUserSession](./Get-RDUserSession.md)
Gets a list of all user sessions in a collection or in a Remote Desktop deployment.

### [Get-RDVirtualDesktop](./Get-RDVirtualDesktop.md)
Gets a list of virtual desktops in the remote desktop deployment.

### [Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)
Gets a list of virtual desktop collections in a remote desktop deployment.

### [Get-RDVirtualDesktopCollectionConfiguration](./Get-RDVirtualDesktopCollectionConfiguration.md)
Gets configuration details of a virtual desktop collection.

### [Get-RDVirtualDesktopCollectionJobStatus](./Get-RDVirtualDesktopCollectionJobStatus.md)
Gets the status of a job on a virtual desktop collection.

### [Get-RDVirtualDesktopConcurrency](./Get-RDVirtualDesktopConcurrency.md)
Gets the number of virtual desktops that RDS can create in parallel.

### [Get-RDVirtualDesktopIdleCount](./Get-RDVirtualDesktopIdleCount.md)
Gets the number of idle virtual desktops on hosts.

### [Get-RDVirtualDesktopTemplateExportPath](./Get-RDVirtualDesktopTemplateExportPath.md)
Gets the export path setting of the virtual desktop template.

### [Get-RDWorkspace](./Get-RDWorkspace.md)
Gets the workspace name for a Remote Desktop deployment.

### [Grant-RDOUAccess](./Grant-RDOUAccess.md)
Grants the Remote Desktop Connection Broker server access to one or more organizational units in a given domain of Active Directory Domain Services.

### [Import-RDPersonalSessionDesktopAssignment](./Import-RDPersonalSessionDesktopAssignment.md)
Imports a map of personal session desktops to users.

### [Import-RDPersonalVirtualDesktopAssignment](./Import-RDPersonalVirtualDesktopAssignment.md)
Imports associations between user accounts and personal virtual desktops from a text file.

### [Invoke-RDUserLogoff](./Invoke-RDUserLogoff.md)
Ends a user session and closes all running applications.

### [Move-RDVirtualDesktop](./Move-RDVirtualDesktop.md)
Moves a virtual desktop to a new Remote Desktop Virtualization Host (RD Virtualization Host) server.

### [New-RDCertificate](./New-RDCertificate.md)
Creates a certificate for an RDS role.

### [New-RDPersonalVirtualDesktopPatchSchedule](./New-RDPersonalVirtualDesktopPatchSchedule.md)
Creates a patch schedule for a personal virtual desktop.

### [New-RDRemoteApp](./New-RDRemoteApp.md)
Publishes a RemoteApp program to a Remote Desktop deployment.

### [New-RDSessionCollection](./New-RDSessionCollection.md)
Creates a session collection of RD Session Host servers.

### [New-RDSessionDeployment](./New-RDSessionDeployment.md)
Installs the required role services for session-based desktop deployment.

### [New-RDVirtualDesktopCollection](./New-RDVirtualDesktopCollection.md)
Creates a virtual desktop collection.

### [New-RDVirtualDesktopDeployment](./New-RDVirtualDesktopDeployment.md)
Installs role services for Virtual Desktop Infrastructure.

### [Remove-RDDatabaseConnectionString](./Remove-RDDatabaseConnectionString.md)
Removes the secondary database connection string for the shared database server in a high availability environment configuration.

### [Remove-RDPersonalSessionDesktopAssignment](./Remove-RDPersonalSessionDesktopAssignment.md)
Removes the association between a personal session desktop assignment and a user.

### [Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)
Removes the association between a personal virtual desktop and a user.

### [Remove-RDPersonalVirtualDesktopPatchSchedule](./Remove-RDPersonalVirtualDesktopPatchSchedule.md)
Removes a patch schedule from a personal virtual desktop.

### [Remove-RDRemoteApp](./Remove-RDRemoteApp.md)
Removes a RemoteApp program.

### [Remove-RDServer](./Remove-RDServer.md)
Removes a server from a Remote Desktop deployment.

### [Remove-RDSessionCollection](./Remove-RDSessionCollection.md)
Removes a session collection from a Remote Desktop deployment.

### [Remove-RDSessionHost](./Remove-RDSessionHost.md)
Removes one or more RD Session Host servers from a session collection.

### [Remove-RDVirtualDesktopCollection](./Remove-RDVirtualDesktopCollection.md)
Removes a virtual desktop collection.

### [Remove-RDVirtualDesktopFromCollection](./Remove-RDVirtualDesktopFromCollection.md)
Removes virtual desktops from a virtual desktop collection.

### [Send-RDUserMessage](./Send-RDUserMessage.md)
Sends a system message to a specified user session.

### [Set-RDActiveManagementServer](./Set-RDActiveManagementServer.md)
Sets the active Remote Desktop Connection Broker  server, or management server, in a remote desktop deployment.

### [Set-RDCertificate](./Set-RDCertificate.md)
Imports and secures a certificate to use with an RDS role.

### [Set-RDClientAccessName](./Set-RDClientAccessName.md)
Sets a DNS name that clients use to connect to a Remote Desktop deployment.

### [Set-RDConnectionBrokerHighAvailability](./Set-RDConnectionBrokerHighAvailability.md)
Sets high availability settings for RD Connection Broker servers for a Remote Desktop deployment.

### [Set-RDDatabaseConnectionString](./Set-RDDatabaseConnectionString.md)
Configures the database connection string for the database server used in a high availability environment.

### [Set-RDDeploymentGatewayConfiguration](./Set-RDDeploymentGatewayConfiguration.md)
Specifies settings for the RD Gateway server for a Remote Desktop deployment.

### [Set-RDFileTypeAssociation](./Set-RDFileTypeAssociation.md)
Changes the file type association of a RemoteApp program in a Remote Desktop deployment.

### [Set-RDLicenseConfiguration](./Set-RDLicenseConfiguration.md)
Defines settings for the RD Licensing server and the licensing mode of the Remote Desktop deployment.

### [Set-RDPersonalSessionDesktopAssignment](./Set-RDPersonalSessionDesktopAssignment.md)
Associates a personal session desktop assignment with a user.

### [Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)
Creates an association between a personal virtual desktop and a user account.

### [Set-RDPersonalVirtualDesktopPatchSchedule](./Set-RDPersonalVirtualDesktopPatchSchedule.md)
Changes patch schedule settings for a personal virtual desktop.

### [Set-RDRemoteApp](./Set-RDRemoteApp.md)
Modifies configuration settings for a RemoteApp program.

### [Set-RDRemoteDesktop](./Set-RDRemoteDesktop.md)
Changes whether to publish a Remote Desktop to a collection.

### [Set-RDSessionCollectionConfiguration](./Set-RDSessionCollectionConfiguration.md)
Modifies configuration options for an existing session collection.

### [Set-RDSessionHost](./Set-RDSessionHost.md)
Configures one or more RD Session Host servers in a session collection.

### [Set-RDVirtualDesktopCollectionConfiguration](./Set-RDVirtualDesktopCollectionConfiguration.md)
Changes configuration settings for a virtual desktop collection.

### [Set-RDVirtualDesktopConcurrency](./Set-RDVirtualDesktopConcurrency.md)
Sets the number of virtual desktops that RDS can create in parallel.

### [Set-RDVirtualDesktopIdleCount](./Set-RDVirtualDesktopIdleCount.md)
Sets the maximum number of idle virtual desktops on host servers.

### [Set-RDVirtualDesktopTemplateExportPath](./Set-RDVirtualDesktopTemplateExportPath.md)
Sets the export path for virtual desktop templates.

### [Set-RDWorkspace](./Set-RDWorkspace.md)
Assigns a workspace name for a Remote Desktop deployment.

### [Stop-RDVirtualDesktopCollectionJob](./Stop-RDVirtualDesktopCollectionJob.md)
Stops a job on a virtual desktop collection.

### [Test-RDOUAccess](./Test-RDOUAccess.md)
Verifies that the Remote Desktop Connection Broker  server can access an Active Directory Domain Services  organizational unit.

### [Test-RDVirtualDesktopADMachineAccountReuse](./Test-RDVirtualDesktopADMachineAccountReuse.md)
Detects whether the RD Connection Broker server is configured to reuse existing AD DS computer accounts.

### [Update-RDVirtualDesktopCollection](./Update-RDVirtualDesktopCollection.md)
Associates a virtual desktop collection with a new virtual desktop template.

