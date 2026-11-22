---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccess_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-remoteaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RemoteAccess
---

# Set-RemoteAccess

## SYNOPSIS
Modifies the configuration that is common to both DirectAccess (DA) and VPN such SSL certificate, Internal interface, and Internet interface.

## SYNTAX

```
Set-RemoteAccess [-SslCertificate <X509Certificate2>] [-ComputerName <String>] [-InternetInterface <String>]
 [-InternalInterface <String>] [-Force] [-PassThru] [-CapacityKbps <UInt64>] [-UseHttp <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RemoteAccess** cmdlet modifies the configuration that is common to both DirectAccess (DA) and VPN such as SSL certificate, Internal interface, and Internet interface.

All settings configured by this cmdlet result in changes only on the server on which the cmdlet is run.
In a network load balancing scenario the SSL certificate changes take effect on all nodes.

As a result, this cmdlet is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-RemoteAccess -InternalInterface 'DomainConnection' -InternetInterface 'Public Network'
```

This example will change the internal and external interfaces configured for DA.
Since in our example setup, DA is deployed in edge topology, the cmdlet will look for the IP configured in ConnectToAddress while installing DA and compare it with the new internet interface IP to make sure that there is a match.

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
Specifies the bandwidth processing capacity of the gateway in Kbps.

```yaml
Type: UInt64
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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access (RA) server computer specific tasks should be run.
If this parameter is specified, then the configuration changes take place on that RA server.

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

### -Force
Forces the command to run without asking for user confirmation.

When suppressed, the cmdlet assumes user confirmation for the following conditions.

 -- Changing the interfaces: This results in re-configuration which is time consuming and the server cannot accept connections during this time.

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

### -InternalInterface
Specifies the name of the corpnet facing interface.

 -- In a single-network-adapter configuration, if the administrator wants to change the interface, then the new name should be specified for both this and the **InternetInterface** parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetInterface
Specifies the name of the internet facing interface.

 -- In a single-network-adapter configuration, if the administrator wants to change the interface, then the new name should be specified for both the **InternalInterface** and this parameters.

 -- When changing the internet interface, if the IP address of the ConnectTo is known, then the IP address of the specified interface is compared with the ConnectTo address.
If there is a mismatch, then the interface is not changed and the cmdlet errors out.
If only the name of ConnectTo is known and it cannot be resolved or if the RA server is deployed behind NAT, then it is assumed that the new interface matches with the ConnectTo address.

```yaml
Type: String
Parameter Sets: (All)
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

### -SslCertificate
Specifies the certificate that will be used to secure remote clients connectivity over HTTPS, in case of DA, or SSTP, in case of VPN.

 -- SSL certificate changes are allowed only within the bounds of the current value of the ConnectTo address (configurable through the Set-DAServer cmdlet), such as the subject name of the new certificate should always match ConnectTo.
All other certificates are rejected and the cmdlet errors out, even if all other criteria for an SSL certificate are satisfied.
This behavior is applicable irrespective of whether NAT is deployed or not and whether the server has a single network adapter or two network adapters.

 -- In a network load balancing scenario the changes take effect on all nodes.
Hence, the specified certificate is required to be present on all nodes in the cluster.

 ---- If the certificate is not found on one or more nodes, then this cmdlet displays an error.

 ---- If one or more nodes are down when changing the certificate, then the change applies only on the nodes that are up.
But the DA server GPO is updated to ensure that when these computers come up load balancing is in stopped state on them due to a certificate mismatch.
For the certificate change to take effect, the administrator needs to install a similar certificate on them and re-run this cmdlet.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UseHttp


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

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

### System.Security.Cryptography.X509Certificates.X509Certificate2

### System.String

### System.Boolean

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessCommon

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessCommon object consists of the following properties:

 -- The status of DA: installed or uninstalled.

 -- The status of VPN: installed or uninstalled.

 -- The status of site-to-site VPN: installed or uninstalled.

 -- The status of load balancing: enabled or disabled.

 -- The name of the internet-facing interface of the RA server.

 -- The name of the internal-facing interface of the RA server.

 -- The SSL certificate which is used for IP-HTTPS and SSTP.

## NOTES

## RELATED LINKS

[Get-RemoteAccess](./Get-RemoteAccess.md)

[Install-RemoteAccess](./Install-RemoteAccess.md)

[Set-DAServer](./Set-DAServer.md)

[Uninstall-RemoteAccess](./Uninstall-RemoteAccess.md)

