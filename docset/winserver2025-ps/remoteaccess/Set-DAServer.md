---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAServer_v2.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAServer
---

# Set-DAServer

## SYNOPSIS
Sets the properties specific to the DirectAccess (DA) server.

## SYNTAX

### EnableComputerCertAuth (Default)
```
Set-DAServer [-ComputerName <String>] [-PassThru] [-Force] [-InternalIPv6Prefix <String[]>]
 [-ClientIPv6Prefix <String>] [-TeredoState <String>] [-ConnectToAddress <String>]
 [-UserAuthentication <String>] [-IPsecRootCertificate <X509Certificate2>] [-IntermediateRootCertificate]
 [-EntrypointName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisableComputerCertAuth
```
Set-DAServer [-ComputerName <String>] [-PassThru] [-Force] [-InternalIPv6Prefix <String[]>]
 [-ClientIPv6Prefix <String>] [-DisableComputerCertAuthentication] [-TeredoState <String>]
 [-ConnectToAddress <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ChangeDAInstallationType
```
Set-DAServer [-ComputerName <String>] -DAInstallType <String> [-PassThru] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAServer** cmdlet sets the properties specific to the DirectAccess (DA) server.

The DA server properties that this cmdlet configures are of the following types.

 -- Properties which are applicable globally to the entire DA deployment.

 -- Properties which are applicable per-server, or per-cluster in a load balancing scenario, or per-site such as in a multi-site deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DAServer -DAInstallType FullInstall -PassThru
Confirm
If the DirectAccess Configuration is changed to FullInstall, DirectAccess client computers will be able to connect to internal network via DirectAccess. Do you want to continue to change DAInstallType?

This cmdlet prompts user to confirm if they really want to change DA configuration. On confirming the cmdlet completes the underlying modifications.
PS C:\>
[Y] Yes  [N] No  [S]Suspend [?] Help  (default is "Y"): Y

DAInstallType               : FullInstall
InternetInterface           : internet
InternalInterface           : datest
ConnectToAddress            : 131.107.0.2
SslCertificate              : [Subject]
CN=131.107.0.2
[Issuer]
CN=131.107.0.2
[Serial Number]
65F63C49B30F669044653F3114390653
[Not Before]
11/29/2011 9:45:23 PM
[Not After]
11/29/2016 1:55:22 PM
[Thumbprint]
0A37103C3038781228FAC19D8725FAD395558FBF
GpoName                     : corp.contoso.com\DirectAccess Server Settings
InternalIPv6Prefix          : 2006:2005:1::/48
ClientIPv6Prefix            : 2006:2005:1:1000::/64
UserAuthentication          : UserPasswd
ComputerCertAuthentication  : Disabled
IPsecRootCertificate        :
IntermediateRootCertificate :
TeredoState                 : Disabled
IsSingleNic                 : False
IsNatDeployed               : False
HealthCheck                 : Disabled
```

This example, given a DA installation in a ManageOut mode, changes the DA configuration to FullInstall mode.
This allows remote clients to connect to resources in the corporate network over the DA connection.

### EXAMPLE 2
```
PS C:\>$certs = Get-ChildItem -Path Cert:\LocalMachine\Root



PS C:\>$IPSecRootCert = $certs[13]



PS C:\>$IPSecRootCert
Directory: Microsoft.PowerShell.Security\Certificate::localmachine\root
Thumbprint                                Subject
----------                                -------
65505D9CDD106DCC6D4C88D3D5FA0EE26B6A3C4F  CN=corp-contoso-dc1-ca


PS C:\>Set-DAServer -IPsecRootCertificate $IPsecRootCert -UserAuthentication "TwoFactor" -PassThru
DAInstallType               : FullInstall
InternetInterface           : internet
InternalInterface           : datest
ConnectToAddress            : 131.107.0.2
SslCertificate              : [Subject]
CN=131.107.0.2
[Issuer]
CN=131.107.0.2
[Serial Number]
65F63C49B30F669044653F3114390653
[Not Before]
11/29/2011 9:45:23 PM
[Not After]
11/29/2016 1:55:22 PM
[Thumbprint]
0A37103C3038781228FAC19D8725FAD395558FBF
GpoName                     : corp.contoso.com\DirectAccess Server Settings
InternalIPv6Prefix          : 2006:2005:1::/48
ClientIPv6Prefix            : 2006:2005:1:1000::/64
UserAuthentication          : TwoFactor
ComputerCertAuthentication  : Enabled
IPsecRootCertificate        : [Subject]
CN=corp-contoso-dc1-ca
[Issuer]
CN=corp-contoso-dc1-ca
[Serial Number]
4022E742A82AECA643E4E786DFE4CB6F
[Not Before]
10/13/2011 8:03:11 AM
[Not After]
10/13/2016 8:13:08 AM
[Thumbprint]
65505D9CDD106DCC6D4C88D3D5FA0EE26B6A3C4F
IntermediateRootCertificate : False
TeredoState                 : Disabled
IsSingleNic                 : False
IsNatDeployed               : False
HealthCheck                 : Disabled
```

This example enables Two-factor user authentication which enables users to use certificates for DA.
There are multiple steps involved in enabling Two-factor authentication.
By default, PKI is disabled during DA installation and will need to be enabled.
This is achieved by provisioning an IPsec root certificate on the DA server using this cmdlet.
The enterprise needs to have a certification authority (CA) which will provision this certificate for all domain joint computers.
The first two steps in this example list out the certificates present in the root certificate store of the server computer and pick an appropriate one.
In this case it happens to be the 13th certificate in the list.
Using this cmdlet, the certificate is then assigned as the IPsec root certificate to enable PKI and the UserAuthentication is specified to be two-factor.

### EXAMPLE 3
```
PS C:\>Set-DAServer -TeredoState Enabled
```

This example enables clients to connect using Teredo.
By default, Teredo is disabled unless two consecutive public IPv4 addresses are found on the internet facing interface of the server while installing DA.
Before enabling Teredo, ensure that two consecutive public IP addresses are present.

### EXAMPLE 4
```
On running the cmdlet, the user is presented with a prompt to confirm the change to the **ConnecToAddress** parameter.
PS C:\>Set-DAServer -ConnectToAddress daserverNew.com
Changing the ConnectTo address will change the certificate used for IPHttps and VPN. If a load balanced cluster is deployed, change will be deployed to all servers in the cluster. Do you want to continue?

On accepting this prompt, the cmdlet tries to locate a certificate for the new connectTo address. In this case it is unable to locate one and tries to create a self-signed certificate.
PS C:\>
[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is "Y"): Y

Certificate IPHttps cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?

Before creating one it asks for user confirmation through the second prompt.
PS C:\>
[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is "Y"): Y
```

This example changes the connectTo address of the DA Server.
However, since the same address is used in IPHttps and VPN certificates, applying this changes the certificates used for both these technologies.

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

### -ClientIPv6Prefix
Specifies the prefix from which IPv6 addresses are assigned to the connecting clients in case of IP-HTTPS.
The length should be 64 bits.
In the case of a load balancing scenario the prefix length should be 59 bits.

The client IPv6 prefix configuration is applicable per-server or per-site as in the case of multi-site deployments.

```yaml
Type: String
Parameter Sets: EnableComputerCertAuth, DisableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the DA server computer specific tasks should be run.

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
Specifies the DA server or NAT public, if DA server is deployed behind a NAT, address to which clients connect.
Specified as host name or IPv4 address.

When the ConnectTo address is changed, the SSL certificate is also changed appropriately.
Following are the rules associated with assigning a proper certificate.

 -- This cmdlet looks for an appropriate SSL certificate on the computer.

 -- If an appropriate SSL certificate is not found, then a self-signed certificate is created.

 -- In the case of external load balancer configuration, if one or more computers are down, then the cmdlet bails out and the ConnectTo Address is not changed.

 -- In a load balancing scenario, if all computers are up and an appropriate SSL certificate is found only on some computers, then the cmdlet fails the operation of changing the ConnectTo address.
If none of the computers has a proper SSL certificate, then a self-signed certificate is created on all computers and the ConnectTo change goes through.
If one or more computers are down, then the certificate is updated only on the other computers.
But the DA server GPO is updated to ensure that when these computers come up load balancing is in stopped state on them due to a certificate mismatch.
For the certificate change, and as a result the ConnectTo address change, to take effect the administrator needs to install a similar certificate with the same name on the computers and re-run this cmdlet.
If a self-signed certificate is being used, then the user just needs to re-run the cmdlet and it automatically creates a self-signed certificate.

 -- In a multi-site scenario, this cmdlet does not create a self-signed certificate and always expects a proper certificate to be present on the computer itself.

The ConnectTo address is applicable per-DA server or per-site, in the case of multi-site deployments.

```yaml
Type: String
Parameter Sets: EnableComputerCertAuth, DisableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAInstallType
Changes the configuration in which DA has been deployed.
The acceptable values for this parameter are:

 -- FullInstall.

 -- ManageOut.

This parameter is a global configuration and applies to the entire DA deployment.

```yaml
Type: String
Parameter Sets: ChangeDAInstallationType
Aliases:
Accepted values: FullInstall, ManageOut

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableComputerCertAuthentication
Specifies that computer certificate authentication is to be disabled.
Disabling this setting disables PKI for the DA deployment.

Following are conditions for computer certificate authentication.

 -- Computer certificate authentication cannot be disabled if health checks are enabled using the **HealthCheck** parameter or Two-factor authentication is used for user authentication or when multi-site deployment is enabled or when firstref_client_7 client support is enabled.

 -- User authentication configuration is automatically changed to `UserPasswd` when computer certificate authentication is disabled.

Computer certificate authentication is re-enabled by configuring an IPsec root certificate using the **IPsecRootCertificate** parameter.

Disabling of computer certificate authentication is a global configuration that applies to the entire DA deployment.

```yaml
Type: SwitchParameter
Parameter Sets: DisableComputerCertAuth
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntrypointName
Specifies the identity of a site in a multi-site deployment and indicates that the DA server properties should be configured for that site.
Only the following properties are applicable at the site level.
The rest of the properties are global and therefore this parameter has no meaning to them.

 -- ClientIPv6Prefix.

 -- ConnectToAddress.

 -- TeredoState.

If this parameter is not specified in a multi-site deployment, then the entry point name to which the server on which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If both this parameter and **ComputerName** parameter are specified and the computer name does not belong to the site represented by the entry point name, then the entry point takes precedence.

```yaml
Type: String
Parameter Sets: EnableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

When suppressed the cmdlet assumes user confirmation for the following conditions.

 -- ConnectTo change would result in a change in the SSL certificate.

 -- During SSL certificate change if an appropriate certificate is not found then a self-signed certificate is created.

 -- Changing DA installation type.

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

### -IPsecRootCertificate
Specifies the root certificate to which DA should chain.
The acceptable values for this parameter are:

 -- Change the IPsec root certificate.

 -- Enable PKI if there is no IPsec root certificate already configured.
However, this cmdlet configures the certificate only on the server on which this cmdlet finally runs.

```yaml
Type: X509Certificate2
Parameter Sets: EnableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IntermediateRootCertificate
Specifies that the IPsec root certificate specified is an intermediate root certificate.

```yaml
Type: SwitchParameter
Parameter Sets: EnableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalIPv6Prefix
Represents the native IPv6 prefixes used in the internal network, in corporate network.
The list of prefixes specified always overwrites the existing list of prefixes.

The list of internal IPv6 prefixes is a global configuration and applies to the entire DA deployment.

```yaml
Type: String[]
Parameter Sets: EnableComputerCertAuth, DisableComputerCertAuth
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -TeredoState
Configures the state of Teredo.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.

The following are the behavioral aspects of Teredo State.

 -- Teredo can be enabled only if two consecutive Public IPv4 addresses are present on the Internet interface of the server.

 -- In a load balancing scenario.

 ---- If a 3rd party load balancer is being used and Teredo has to be enabled, then the load balancer should have two consecutive IP addresses.
Additionally each DA server that is part of the Load balancer must have 2 consecutive public IPv4 addresses.

 ---- Teredo can be enabled on a cluster if the cluster has VIPs that are two consecutive public IPv4 addresses.
If such IPs are not found, then the cluster should be destroyed first and two consecutive IPs should be configured on the DA server.

 -- The Teredo configuration is applicable per-computer or per-site, in the case of multi-site deployments.

```yaml
Type: String
Parameter Sets: EnableComputerCertAuth, DisableComputerCertAuth
Aliases:
Accepted values: Enabled, Disabled

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

### -UserAuthentication
Sets the type of authentication that is used to authenticate a DA user.
The acceptable values for this parameter are:

 -- TwoFactor.

 -- UserPasswd.

Here two-factor refers to certificate authentication, OTP authentication, or smartcard based authentication.
Note: To setup OTP authentication enabling two-factor alone is not enough.
It needs to be configured separately using the DAOtpAuth cmdlets.

User authentication is a global configuration that applies to the entire DA deployment.

```yaml
Type: String
Parameter Sets: EnableComputerCertAuth
Aliases:
Accepted values: TwoFactor, UserPasswd

Required: False
Position: Named
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

### System.String[]

### System.Security.Cryptography.X509Certificates.X509Certificate2

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties:

 -- Type of DirectAccess installation: full or managed.

 -- Authentication type.

 -- Internal IPv6 prefix.

 -- Client IPHTTPS IPv6 prefix.

 -- Usage of computer certificate authorization for 1st tunnel: Enabled or Disabled.

 -- IPsec root certificate.

 -- Whether the IPsec root certificate is an intermediate root certificate.

 -- Status of Teredo: Enabled or Disabled.

 -- Whether the DA server is deployed behind NAT.

 -- Whether the configuration in which DA is deployed is a single or double network adapter.

 -- Name of the DA server GPO.

 -- Status of the health check.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=204557)

[Get-DAServer](./Get-DAServer.md)

[Get-RemoteAccess](./Get-RemoteAccess.md)

