---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DANetworkLocationServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-danetworklocationserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DANetworkLocationServer
---

# Get-DANetworkLocationServer

## SYNOPSIS
Displays the detailed Network Location Server (NLS) configuration.

## SYNTAX

```
Get-DANetworkLocationServer [-CheckReachability] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DANetworkLocationServer** cmdlet displays the detailed Network Location Server (NLS) configuration.

Configuration consists of the following.

 -- Where the NLS is present, such as on DirectAccess (DA) Server or some other external server.

 -- URL, if the NLS is present on a different server.

 -- Whether the NLS is reachable or if it is configured on a different server.

 -- NLS Certificate, if the NLS is present on the DA server.

 -- Reachability: If the NLS is present on an external server, then is it reachable.
If the **CheckReachability** parameter is specified, then this configuration is populated.

The configuration returned is applicable, globally, to the entire deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DANetworkLocationServer -CheckReachability
NLSLocation : DirectAccessServer
URL  :
Reachability : True
Certificate :[Subject]
CN=edge1.corp.contoso.com
 [Issuer]
CN=corp-DC1-DA
 [Serial Number]
611C450F000000000003
 [Not Before]
10/3/2011 7:42:23 PM
 [Not After]
10/2/2012 7:42:23 PM
 [Thumbprint]
23SF6B23J076HJ6LW6LD7H4L62206K237SNH6G2F
```

This example gets the NS configuration for the DA deployment.
In this case since the DA Server is hosting the NLS, the NLS Location is shown to be DA Server.
The output also shows the SSL certificate which is being used by NLS.

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

### -CheckReachability
Performs a reachability check to the specified URL.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DANetworkLocationServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The object consists of the following properties:

 -- Where the NLS is configured: on the DA server or on a different server.

 -- If NLS is configured on a different server: the URL used to detect whether a remote computer is inside or outside the corporate network.

 -- The certificate used for NLS if it is configured on the DA server.

 -- If the NLS is on a different server, then whether the URL is reachable or not.

## NOTES

## RELATED LINKS

[Set-DANetworkLocationServer](./Set-DANetworkLocationServer.md)

