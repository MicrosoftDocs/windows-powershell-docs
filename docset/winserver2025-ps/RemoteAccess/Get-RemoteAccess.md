---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccess_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccess
---

# Get-RemoteAccess

## SYNOPSIS
Displays the configuration of DirectAccess (DA) and VPN (both Remote Access VPN and site-to-site VPN).

## SYNTAX

```
Get-RemoteAccess [-ComputerName <String>] [[-EntrypointName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccess** cmdlet displays the configuration of DirectAccess (DA) and VPN (both Remote Access VPN and site-to-site VPN).

The output consists of the following.
If a certain Remote Access technology (RA) is not installed, then only the computer status is displayed.

 -- Status of DA.

 -- Status of VPN.

 -- Status of site-to-site VPN.

 -- Status of Load Balancing.

 -- DA global configuration: Comprises of properties that are applicable to the entire DA deployment.

 -- DA server level or cluster level (if load balancing has been deployed) configuration.
If multi-site is deployed, then this configuration is applicable at the site-level and configuration for the specified site is displayed.

 -- DA pure server and cluster level configuration: This configuration is not impacted by multi-site deployment.

 -- VPN server or cluster level configuration.
If multi-site is deployed, then this configuration is applicable at the site-level and configuration for the specified site is displayed.

 -- VPN pure server level configuration: This configuration is not impacted by multi-site deployment.

In a multi-site deployment if both the **EntryPointName** and **ComputerName** parameters are specified but the computer name does not belong to that entry point name, then no values are returned for the pure server-level DA and VPN (both Remote Access VPN and site-to-site VPN)configuration.
The configuration will show up blank.
However, if only the **EntryPointName** parameter is specified or the **ComputerName** parameter is also specified and belongs to the specified entry point name, then the pure server-level DA and VPN configuration are retrieved if the server on which the cmdlet is run belongs to this entry point.
If not, then blanks are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccess
DAStatus                       : Installed
DAInstallType                  : FullInstall
VpnStatus                      : Installed
VpnS2SStatus                   : Uninstalled
LoadBalancing                  : NotConfigured
ConnectToAddress               : 192.168.0.2
InternetInterface              : Private Internet
InternalInterface              : Private Corpnet
SslCertificate                 : [Subject]
                                   CN=192.168.0.2

                                 [Issuer]
                                   CN=192.168.0.2

                                 [Serial Number]
                                   42242E616EC4CD994F9C4BE8E33ABBFE

                                 [Not Before]
                                   23-01-2012 03:21:52

                                 [Not After]
                                   22-01-2017 19:31:51

                                 [Thumbprint]
                                   D9BB778F6F1111111F5B3E2F55DDD9F00B9C2F5A

AppServerSecurityGroupNameList :
AppServerGpoName               :
ConnectionType                 : NoE2EAuth
TrafficProtection              : Disabled
ClientSecurityGroupNameList    : contoso.com\Domain Computers
ClientGpoName                  : contoso.com\DirectAccess Client Settings
OnlyRemoteComputers            : Enabled
Downlevel                      : Disabled
ForceTunnel                    : Disabled
ForceTunnelingNrptSuffix       :
EntrypointName                 :
DownlevelSecurityGroupNameList :
DownlevelGpoName               :
DnsSuffix                      : {.contoso.com, directaccess-nls.contoso.com}
EnableDAForAllNetworks         : Disable
SecureNameQueryFallback        : FallbackPrivate
QueryPolicy                    : Disable
ServerGpoName                  : contoso.com\DirectAccess Server Settings
InternalIPv6Prefix             : 2002:836b:1:1::/64
ClientIPv6Prefix               : 2002:836b:1:1000::/64
UserAuthentication             : UserPasswd
ComputerCertAuthentication     : Disabled
IPsecRootCertificate           :
IntermediateRootCertificate    : False
TeredoState                    : Disabled
IsSingleNic                    : False
IsNatDeployed                  : False
HealthCheck                    : Disabled
NlsLocation                    : DirectAccessServer
NlsUrl                         :
NlsCertificate                 : [Subject]
                                   CN=directaccess-nls.contoso.com

                                 [Issuer]
                                   CN=directaccess-nls.contoso.com

                                 [Serial Number]
                                   444D9B8E0A7777777D00000000000DDD

                                 [Not Before]
                                   23-01-2012 03:21:51

                                 [Not After]
                                   22-01-2017 19:31:51

                                 [Thumbprint]
                                   F1111D88EE6C33B777777EEE2CC4444777777DD7

NlsReachability                : False
MgmtServer                     :
IPAssignmentMethod             : StaticPool
IPAddressRangeList             : {10.1.1.10 - 10.1.1.30, 10.10.1.10 - 10.10.1.30}
IPv6Prefix                     : 2002:836b:1:2000::/64
AuthenticationType             : Windows
RadiusServerList               :
```

This example displays the configuration of DA and VPN for the local computer.

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

### -EntrypointName
Specifies the identity of a site in a multi-site deployment.
If this parameter is not specified, then the site to which the computer on which this cmdlet is run is used (the user may or may not be specifying a computer name).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessCommon

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessCommon object consists of the following properties:

 -- The status of the DA and VPN configuration.

 -- The entire VPN configuration.

 -- The entire DA configuration.

 -- The configuration common to both VPN and DA.

## NOTES

## RELATED LINKS

[Install-RemoteAccess](./Install-RemoteAccess.md)

[Set-RemoteAccess](./Set-RemoteAccess.md)

[Uninstall-RemoteAccess](./Uninstall-RemoteAccess.md)

