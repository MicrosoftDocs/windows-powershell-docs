---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAServer_v2.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAServer
---

# Get-DAServer

## SYNOPSIS
Displays the properties of the DirectAccess (DA) server.

## SYNTAX

```
Get-DAServer [-ComputerName <String>] [[-EntrypointName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAServer** cmdlet displays the properties of the DirectAccess (DA) server.

The output displayed consists of the following.

Global Configuration: These properties are applicable to the entire DA deployment.

 -- DA installation configuration: full install or only manage-out.

 -- Internal IPv6 prefix.

 -- Authentication type.

 -- IPsec root certificate: The certificate is always configured separately on every server, although the same certificate issued by same root is present on all DA servers.

 -- Intermediate root certificate usage: enabled or disabled.

 -- Computer certificate authentication: enabled or disabled.

 -- DA server GPO name.

 -- Health check: enabled or disabled.

For the following properties either the server-level or cluster level, if load balancing has been deployed, configuration is returned.
If multi-site is deployed, then this configuration is applicable at the site-level and configuration for the specified site is displayed.

 -- Client IPv6 prefix.

 -- Teredo State.

 -- Whether NAT is enabled.

 -- Does DA server have a single network adapter or two network adapters.

The following are pure server-level properties that are returned.
In a multi-site deployment if both the **EntryPointName** and **ComputerName** parameters are specified, but the **ComputerName** parameter value does not belong to that entry point name, then no values are returned for these properties.
However, if only the **EntryPointName** parameter is specified or the **ComputerName** parameter value is also specified and belongs to the specified entry point name, then the configuration is retrieved from the server on which the cmdlet is run as follows.

 -- Internet interface.

 -- Internal interface.

 -- SSL certificate.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAServer
DAInstallType               : FullInstall
InternetInterface           : Private Internet
InternalInterface           : Private Corpnet
ConnectToAddress            : 192.168.0.2
SslCertificate              : [Subject]
                                CN=192.168.0.2

                              [Issuer]
                                CN=192.168.0.2

                              [Serial Number]
                                44442E555EE4CC999F9C4BB8E33AAAAA

                              [Not Before]
                                23-01-2012 03:21:52

                              [Not After]
                                22-01-2017 19:31:51

                              [Thumbprint]
                                D9BB718F6F1502967F5B3E2F59DEE9F00B9C2F5A

GpoName                     : contoso.com\DirectAccess Server Settings
InternalIPv6Prefix          : 2002:836B:1:1::/64
ClientIPv6Prefix            : 2002:836B:1:1000::/64
UserAuthentication          : UserPasswd
ComputerCertAuthentication  : Disabled
IPsecRootCertificate        :
IntermediateRootCertificate : False
TeredoState                 : Disabled
IsSingleNic                 : False
IsNatDeployed               : False
HealthCheck                 : Disabled
```

This example displays the properties of the local DA server.

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

### -EntrypointName
Specifies the identity of a site in a multi-site deployment and when specified indicates that the configuration of the DA server at that site should be retrieved.

If this parameter is not specified in a multi-site deployment then the entry point to which the server on which this cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If both this parameter and **ComputerName** parameter are specified and the computer name does not belong to the site represented by this parameter then this parameter takes precedence and the configuration is returned for it.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DAServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties:

 -- Type of DA installation: full or managed.

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

[Get-DAServer](./Get-DAServer.md)

[Get-RemoteAccess](./Get-RemoteAccess.md)

