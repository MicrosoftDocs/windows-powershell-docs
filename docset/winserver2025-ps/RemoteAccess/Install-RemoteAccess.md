---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccess_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/install-remoteaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-RemoteAccess
---

# Install-RemoteAccess

## SYNOPSIS
Performs prerequisite checks for DirectAccess (DA) to ensure that it can be installed, installs DA for remote access (RA) (includes management of remote clients) or for management of remote clients only, installs VPN (both Remote Access VPN and site-to-site VPN), and installs Border Gateway Protocol Routing..

## SYNTAX

### DirectAccess (Default)
```
Install-RemoteAccess [-ComputerName <String>] [-DAInstallType] <String> [-ClientGpoName <String>]
 [-InternalInterface <String>] [-InternetInterface <String>] [-NlsCertificate <X509Certificate2>]
 [-NlsUrl <String>] [-NoPrerequisite] [-ServerGpoName <String>] [-ConnectToAddress] <String> [-DeployNat]
 [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Vpn
```
Install-RemoteAccess [-ComputerName <String>] [-PassThru] [-VpnType] <String> [-MsgAuthenticator <String>]
 [-RadiusPort <UInt16>] [-RadiusScore <Byte>] [-RadiusServer <String>] [-RadiusTimeout <UInt32>]
 [-SharedSecret <String>] [-Legacy] [-IPAddressRange <String[]>] [-IPv6Prefix <String>]
 [-EntrypointName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MultiTenant
```
Install-RemoteAccess [-ComputerName <String>] [-PassThru] [-MultiTenancy] [[-VpnType] <String>]
 [-MsgAuthenticator <String>] [-RadiusPort <UInt16>] [-RadiusScore <Byte>] [-RadiusServer <String>]
 [-RadiusTimeout <UInt32>] [-SharedSecret <String>] [-CapacityKbps <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DAPrerequisiteChecks
```
Install-RemoteAccess [-ComputerName <String>] [-Prerequisite] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-RemoteAccess** cmdlet performs prerequisite checks for DirectAccess (DA) to ensure that it can be installed, installs DA for remote access (RA) (includes management of remote clients) or for management of remote clients only, installs VPN (both Remote Access VPN and site-to-site VPN), and installs Border Gateway Protocol Routing.

Prerequisite Checks.
- Every prerequisite check results in a terminating, non-terminating error, or a warning.
- The only terminating error condition is DA server not joined to a domain or the Active Directory server not being reachable and it results in the immediate stopping of the cmdlet.
- If the cmdlet performs only prerequisite checks, then the user is informed about every check that fails, through an appropriate message.
- If prerequisite checks are performed just before installation, such as the **NoPreRequisite** parameter is not specified, then the cmdlet performs all checks one after the other without displaying any messages for failed checks.
If one or more terminating or non-terminating errors are encountered, then the cmdlet does not proceed with the installation.
If all checks pass or only warnings are encountered, then the cmdlet proceeds with installation.

Re-using Existing Configuration.
If one of the remote access technologies is already installed and the cmdlet is used to install the other technology, then it tries to use as much of the configuration of the installed technology as possible and handles any discrepancies between the two technologies.
There are separate parameter sets for DA and VPN installation.
If the user specifies parameters, that can be re-used from the existing configuration they are ignored.
Example: If VPN is already enabled and a user specifies the internal and internet interfaces ,then when installing DA they are ignored and the cmdlets uses the existing VPN interfaces.

Note: This cmdlet cannot be used to move from one DA installation type to another.
Run the Set-DAServer cmdlet to move one DA installation type to another.

DA Installation.
 Client configuration:
- By default DA is deployed on all domain laptop and netbook computers that belong to the domain specified in the client GPO.
This is achieved by adding the Domain Computers AD group as the client SG and creating a WMI filter to filter out devices that are classified as either non-laptops and netbooks.
If a client GPO is not specified then the domain of the DA server is used and a client GPO with default name is created in that domain.
If the user running the cmdlet does not have the permissions to create the WMI filter, then no client SG is added.
- Force tunneling is disabled for the clients.
- This cmdlet does not deploy DA on down-level clients.
DA Server configuration.
- If a GPO with the specified name or default name is not present, then it is created.
If it is found, then it is edited with the DA server settings.
- Selecting the internal and internet interfaces.
- The internal and internet interfaces can be specified in the cmdlet.
If the user wishes to deploy DA in a single network adapter configuration, then the same name should be specified for both interfaces.
- If one or none of them is specified, then the cmdlet itself selects the appropriate interfaces based on their configuration.
- If a VPN is already installed and the interfaces were specified during its installation, then the same interfaces are re-used.
If the interfaces were not specified during VPN installation, then the user is allowed to manually specify the interfaces or the cmdlet picks them itself.
- Transition Technologies: IPHTTPS is always enabled.
Teredo is enabled only if 2 consecutive IP addresses are found on the internet interface.
- User authentication: All DA users are authenticated using their domain user name and password.
- IPv6 deployment in internal network: If a native IPv6 deployment is detected inside corporate network, then its IPv6 prefix is obtained.
Otherwise ISATAP is automatically deployed.
Note: That ISATAP will not become effective until the DNS is configured to resolve ISATAP.
- DA is installed in a PKI-less mode, i.e.
no IPsec root certificate is required.
- A certificate is still required for IPHTTPS: If VPN is already installed, then the SSL certificate for SSTP is re-used.
If there is no certificate configured for VPN, then the cmdlet looks for an appropriate certificate on the computer (a certificate that matches the **ConnectToAddress** parameter value) or generates a self-signed certificate.
Infrastructure Server configuration.
- If the NLS location is not specified in the cmdlet, then it is deployed on the DA server by default.
The cmdlet looks for a certificate for which the subject name matches the internal interface of the DA server.
If an appropriate certificate cannot be found, then a self-signed certificate is generated.
- Health checks are not enabled during installation.
- Application servers are not configured during installation.
- If an IPv4 address is detected on the internal interface of the DA server, then the DNS64 or NAT64 configuration is enabled on the DA server which enables DA clients to access corporate network resources that have IPv4 address only by allotting v6 addresses to these hosts.
- This cmdlet also does an auto-discovery of Configuration Manager servers including Domain Controllers and configures them as the Management Servers.

VPN Installation.
Authentication configuration.
By default Windows authentication is enabled.
This also includes authentication through NPS installed locally on the VPN server.
If a RADIUS server is specified, then external RADIUS authentication is used.
 IP address assignment configuration.
- IPv4 addressing with DHCP address assignment is enabled by default.
If an IP address range is specified, then static pool addressing is used.
- IPv6 addressing is disabled by default.
If an IPv6 prefix is specified, then v6 addressing is enabled and the prefix is used for the addresses.

## EXAMPLES

### Example 1: Log in as a test user and display error message
```
PS C:\>Install-RemoteAccess -PreRequisite
Warning: The current user does not have the required permissions to configure WMI filtering in the domain. Verify permissions.
Install-RemoteAccess : DirectAccess can only be configured by a user with local administrator permissions on the server. Add the current user to local administrator group
At line:1 char 1
+ install-remoteaccess -prerequisite
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+CategoryInfo : NotSpecified: (ServerProvider:root/Microsoft/...PS_RemoteAccess) [Install-RemoteAccess], CimException
+ FullyQualifiedErrorId : REMOTEACCESSERROR 104, Install-RemoteAccess
```

This command logs in as a test user who is not a domain user or an administrator on the server.
This results in the error specifying that DA can only be configured by a user with local administrator permissions.

### Example 2: Install DirectAccess to allow remote clients to connect to corporate network
```
PS C:\>$RemAccess = Install-RemoteAccess -DAInstallType FullInstall -ConnectToAddress edge1.contoso.com -PassThru
Confirm

 Installing Remote Access will configure this computer as a Remote Access server. Do you want to install Remote Access?
[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is "Y"): Y

Note: The cmdlet automatically creates a Server and a Client GPO with Default names in the domain to which the current computer is connected. The Client GPO will be filtered on Domain Computers Security Group by default. The default settings can be modified using Set-DAClient.

This cmdlet will prompt the user that IPsec and Firewall Policies will be updated. It will automatically try and locate a certificate for NLS and IP-HTTPS (SSL cert), in case it does not find these the cmdlet will prompt the user to create a self-signed certificate for the ones not found.
PS C:\>$RemAccess.DAStatus
Installed

Install-RemoteAccess : The external network adapter settings cannot be determined automatically on localhost. Run the cmdlet again and specify the adapter settings

At line:1 char:1

+ Install-RemoteAccess -DAInstallType FullInstall -ConnectToAddress edge1.contoso.com

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

+CategoryInfo: ObjectNotFound: (MgmtProvider:root/Microsoft:...PS_RemoteAccess) [Install-RemoteAccess], CimException

+ FullyQualifiedErrorId : REMOTEACCESSERROR 112, Install-RemoteAccess
```

This command installs DA to allow remote clients to connect to corporate network.
This cmdlet searches for Internet interface and Internal interfaces.
If it finds both these interfaces (as in this example), the cmdlet configures DA in edge topology.
In case the cmdlet does not find a public interface and the **DeployNat** parameter is not specified, the cmdlet will display the following error.

### Example 3: Deploy DirectAccess behind another edge device
```
PS C:\>Install-RemoteAccess -DAInstallType FullInstall -ConnectToAddress nat1.contoso.com -InternalInterface 'Internal Connection' -InternetInterface 'Internal Connection' -DeployNat
```

This command will deploy DA behind another edge device (NAT box).
In the example setup, the DA server has a single network adapter connected to the corporate network named corp.contoso.com.
Note: The public interface of the NAT device is the one used in **ConnectToAddress** parameter.
For a single network adapter behind NAT topology, the **InternalInterface** and **InternetInterface** parameters need to be mentioned, or the cmdlet will display an error that an external interface was not found.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CapacityKbps
Specifies thebandwidth processing capacity of the gateway in Kbps.

```yaml
Type: UInt64
Parameter Sets: MultiTenant
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientGpoName
Specifies the names of the client GPO.
The GPO name is specified in `DOMAIN\GPO_NAME` format.
A domain can be one of the domains deployed in the corporate network.
If a GPO name is not specified, then by default a GPO with following name is created in the domain of the DA server:
- DirectAccess Client Settings.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases: GpoName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectToAddress
Specifies the DA server or NAT public address to which the clients connect.
Specified as a host name or an IPv4 address.
If the address is specified, then is must to be public.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAInstallType
Specifies the configuration in which DA should be installed.
The acceptable values for this parameter are:
- FullInstall: DA is installed for both remote access and for the management of remote clients.
- ManageOut: DA is installed only for the management of remote clients.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:
Accepted values: FullInstall, ManageOut

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeployNat
Specifies that DA should be deployed behind a NAT.
In a single network adapter configuration scenario the DA server is always deployed behind a NAT and there is no need to specify this parameter.

```yaml
Type: SwitchParameter
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntrypointName
Specifies the identity of a site in a multi-site deployment where VPN needs to be installed.
This is required in a scenario where DA with multi-site is already deployed and a user wants to additionally deploy VPN.
If this parameter is not specified, then the entry point name to which the server on which the cmdlet is run is used.
The server could also be represented using the **ComputerName** parameter.

If both this parameter and **ComputerName** parameter are specified and the computer name does not belong to the site represented by the entry point name then this parameter takes precedence and VPN is deployed at the site indicated by it.
Note: A multi-site deployment case VPN can only be installed one site at a time.
Note: In a S2S case, the cmdlet will install it on any one available node in that entry point.

```yaml
Type: String
Parameter Sets: Vpn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.
When suppressed, the cmdlet assumes user confirmation for the following conditions.
- If an appropriate certificate for NLS is not found, then a self-signed certificate is created.
- If an appropriate SSL certificate is not found, then a self-signed certificate is created.
Note: If the addresses are not static (such as DHCP), then ShouldContinue can be used.

```yaml
Type: SwitchParameter
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressRange
Specifies that static pool IPv4 addressing should be enabled.
This parameter contains an IP address range, and consisting of a start IP and an end IP, from which IP addresses are allocated to VPN clients.
In a load balancing scenario only static pool IPv4 addressing is supported for a VPN (DHCP address assignment is not supported).
This parameter must be specified and an IPv4 address range should be provided for every node in the cluster.
This parameter is specified in the following format:
`StartIPRange1, EndIPRange1, StartIPRange2, EndIPRange2, StartIPRange3, EndIPRange3`, and so on.
The start and end IPs of each of the ranges must be specified one after the other and separated by commas.

```yaml
Type: String[]
Parameter Sets: Vpn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Prefix
Enables IPv6 address assignment for a VPN and specifies the prefix to use for the addressing.

```yaml
Type: String
Parameter Sets: Vpn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalInterface
Specifies the name of the corporate network facing interface.
In a single network adapter configuration the same name is specified for both internal and internet interfaces.
If a name is not specified, then the cmdlet attempts to detect the internal interface automatically.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetInterface
Specifies the name of the internet facing interface.
In a single network adapter configuration the same name is specified for both internal and internet interfaces.
If name is not specified, then this cmdlet attempts to detect the internet interface automatically.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Legacy


```yaml
Type: SwitchParameter
Parameter Sets: Vpn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsgAuthenticator
Specifies that the usage of message authenticator should be enabled or disabled.
The acceptable values for this parameter are:
- Enabled.
- Disabled.
The default value is Disabled.
This parameter is applicable only when a RADIUS server is being configured for authentication.

```yaml
Type: String
Parameter Sets: Vpn
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: MultiTenant
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MultiTenancy
Indicates that multitenancy is enabled for the service.

```yaml
Type: SwitchParameter
Parameter Sets: MultiTenant
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NlsCertificate
Specifies that the Network Location Server (NLS) should be configured on the DA server itself and represents the certificate to be used.
The subject name of the certificate should resolve to an address on the internal interface of the DA server.

```yaml
Type: X509Certificate2
Parameter Sets: DirectAccess
Aliases: Certificate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NlsUrl
Specifies that the NLS is present on a different server and represents the URL on the server that will be used to provide clients with location information.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoPrerequisite
Specifies that a prerequisite check should not be performed for DA.

```yaml
Type: SwitchParameter
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: DirectAccess, Vpn, MultiTenant
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prerequisite
Specifies that prerequisite checks should be performed.
This parameter is part of a separate parameter set used to only run the prerequisite checks for DA.

```yaml
Type: SwitchParameter
Parameter Sets: DAPrerequisiteChecks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RadiusPort
Specifies the port number on which the RADIUS server is accepting authentication requests.
The default value is 1813.
This parameter is applicable only when a RADIUS server is being configured for authentication.

```yaml
Type: UInt16
Parameter Sets: Vpn
Aliases: Port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: UInt16
Parameter Sets: MultiTenant
Aliases: Port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusScore
Specifies the initial score for the RADIUS server.
The default value is 30.
This parameter is applicable only when a RADIUS server is being configured for authentication.

```yaml
Type: Byte
Parameter Sets: Vpn
Aliases: Score

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Byte
Parameter Sets: MultiTenant
Aliases: Score

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServer
Specifies the IPv4 or IPv6 address, or host name, of the RADIUS server that is to be used for authentication.
Specifying this parameter indicates that RADIUS authentication should be used for VPN.

```yaml
Type: String
Parameter Sets: Vpn
Aliases: ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: MultiTenant
Aliases: ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusTimeout
Specifies the timeout value for the RADIUS server, in seconds.
The default value is 5 seconds.
This parameter is applicable only when a RADIUS server is being configured for authentication.

```yaml
Type: UInt32
Parameter Sets: Vpn
Aliases: Timeout

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: UInt32
Parameter Sets: MultiTenant
Aliases: Timeout

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerGpoName
Specifies the name of the GPO for the DA server.
Specified in the format `DOMAIN\GPO_NAME`.
If a name is not specified, then a GPO with the following name is created in the domain of a DA server:
 -- DirectAccess Client Settings.

```yaml
Type: String
Parameter Sets: DirectAccess
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret between the RA server and the specified external RADIUS server, which is required for successful communication between the two servers.
Note: The secret is specified in plain text.
It is mandatory to specify this parameter if a RADIUS server is being configured for authentication.

```yaml
Type: String
Parameter Sets: Vpn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: MultiTenant
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VpnType
Specifies the type of VPN installation.
The acceptable values for this parameter are:
- Vpn
- VpnS2S
- SstpProxy
- RoutingOnly

```yaml
Type: String
Parameter Sets: Vpn
Aliases: RoleType
Accepted values: Vpn, VpnS2S, SstpProxy, RoutingOnly

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: MultiTenant
Aliases: RoleType
Accepted values: Vpn, VpnS2S, SstpProxy, RoutingOnly

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.Cryptography.X509Certificates.X509Certificate2

### System.Management.Automation.SwitchParameter

### System.UInt16

### System.Byte

### System.UInt32

### System.String[]

## OUTPUTS

### System.Boolean

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessCommon

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The RemoteAccessCommon object consists of the following properties:
- The status of DirectAccess: installed or uninstalled.
 -- The status of VPN: installed or uninstalled.
 -- The status of site-to-site VPN: installed or uninstalled.
- The status of load balancing: enabled or disabled.
- The name of the internet-facing interface of the Remote Access server.
- The name of the internal-facing interface of the Remote Access server.
- The SSL certificate which is used for IP-HTTPS and SSTP.

## NOTES

## RELATED LINKS

[Add-VpnS2SInterface](./Add-VpnS2SInterface.md)

[Get-RemoteAccess](./Get-RemoteAccess.md)

[Set-DAClient](./Set-DAClient.md)

[Set-DAServer](./Set-DAServer.md)

[Set-RemoteAccess](./Set-RemoteAccess.md)

[Uninstall-RemoteAccess](./Uninstall-RemoteAccess.md)
