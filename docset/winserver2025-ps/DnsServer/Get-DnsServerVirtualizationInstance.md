---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerVirtualizationInstance_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsservervirtualizationinstance?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerVirtualizationInstance
---

# Get-DnsServerVirtualizationInstance

## SYNOPSIS
Gets the virtualization instances on the DNS server.

## SYNTAX

```
Get-DnsServerVirtualizationInstance [-ComputerName <String>] [[-Name] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerVirtualizationInstance** cmdlet gets the virtualization instances on the Domain Name System (DNS) server.
If the *Name* parameter is provided then the cmdlet returns that virtualization instance.

## EXAMPLES

### Example 1: Display information about a virtualization instance
```
PS C:\> Get-DnsServerVirtualizationInstance -Name 8231 | fl *
Description            : This virtualization instance hosts the zones for the Host tenant
FriendlyName           : HostTenantPartition
VirtualizationInstance : 8231
PSComputerName         :
CimClass               : root/Microsoft/Windows/DNS:DnsServerVirtualizationInstance
CimInstanceProperties  : {Description, FriendlyName, VirtualizationInstance}
CimSystemProperties    : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command displays information about the virtualization instance named 8231.

### Example 2: Show all virtualization instances on the DNS server
```
PS C:\> Get-DnsServerVirtualizationInstance | fl *
Description            :
FriendlyName           : Default
VirtualizationInstance : .
PSComputerName         :
CimClass               : root/Microsoft/Windows/DNS:DnsServerVirtualizationInstance
CimInstanceProperties  : {Description, FriendlyName, VirtualizationInstance}
CimSystemProperties    : Microsoft.Management.Infrastructure.CimSystemProperties

Description            : This virtualization instance hosts the zones for the 'Host' tenant
FriendlyName           : RedTenantPartition
VirtualizationInstance : 8231
PSComputerName         :
CimClass               : root/Microsoft/Windows/DNS:DnsServerVirtualizationInstance
CimInstanceProperties  : {Description, FriendlyName, VirtualizationInstance}
CimSystemProperties    : Microsoft.Management.Infrastructure.CimSystemProperties
Description            : This virtualization instance hosts the zones for tenant blue
FriendlyName           : TenantBluePartition
VirtualizationInstance : 9743
PSComputerName         :
CimClass               : root/Microsoft/Windows/DNS:DnsServerVirtualizationInstance
CimInstanceProperties  : {Description, FriendlyName, VirtualizationInstance}
CimSystemProperties    : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command shows the virtualization instances on the DNS server including the default virtualization instance represented by a period.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies the remote computer on which this cmdlet executes the command.
Type the NetBIOS name, or a fully qualified domain name of a remote computer.

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

### -Name
Specifies, as a string array, the unique identifier of the virtualization instance.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: VirtualizationInstance

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerVirtualizationInstance[]

## NOTES

## RELATED LINKS

[Add-DnsServerVirtualizationInstance](./Add-DnsServerVirtualizationInstance.md)

[Remove-DnsServerVirtualizationInstance](./Remove-DnsServerVirtualizationInstance.md)

[Set-DnsServerVirtualizationInstance](./Set-DnsServerVirtualizationInstance.md)

