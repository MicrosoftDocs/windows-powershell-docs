---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClientDNSConfiguration_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daclientdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAClientDnsConfiguration
---

# Get-DAClientDnsConfiguration

## SYNOPSIS
Displays all the Name Resolution Policy Table (NRPT) entries and the local name resolution property.

## SYNTAX

```
Get-DAClientDnsConfiguration [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAClientDNSConfiguration** cmdlet displays all the Name Resolution Policy Table (NRPT) entries and the local name resolution property.

Specifically, the following properties are displayed.

 -- List of suffixes.

 -- DirectAccess (DA) rules state.

 -- DNS client Local Name resolution fallback policy.

 -- DNS client query policy (Disable, QueryIPv6Only, or QueryBoth).

The configuration returned is applicable, globally, to the entire DA deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAClientDNSConfiguration
NrptSuffixes   : {.corp.contoso.com, edge1.corp.contoso.com}
EnableDAForAllNetworks  : Disable
SecureNameQueryFallback : FallbackPrivate
QueryPolicy             : Disable
```

This example gets the NRPT configuration for the DA deployment.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### Microsoft.Management.Infrastructure.CimInstance#DAClientDnsConfiguration

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties:

 -- The NRPT entries in the NRPT table.
Each entry is an instance of the **DnsClientNrptRule** object.

 -- The **DnsClientNrptGlobal** object which contains the local name resolution settings.

## NOTES

## RELATED LINKS

[Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)

[Remove-DAClientDnsConfiguration](./Remove-DAClientDnsConfiguration.md)

[Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)

