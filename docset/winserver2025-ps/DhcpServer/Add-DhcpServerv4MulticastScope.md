---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4MulticastScope_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4multicastscope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4MulticastScope
---

# Add-DhcpServerv4MulticastScope

## SYNOPSIS
Adds a multicast scope on the DHCP server.

## SYNTAX

```
Add-DhcpServerv4MulticastScope [-ComputerName <String>] [-Name] <String> [-StartRange] <IPAddress>
 [-EndRange] <IPAddress> [-Description <String>] [-State <String>] [-LeaseDuration <TimeSpan>] [-PassThru]
 [-Ttl <UInt32>] [-ExpiryTime <DateTime>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4MulticastScope** cmdlet adds a multicast scope on the Dynamic Host Configuration Protocol (DHCP) server.

## EXAMPLES

### Example 1: Add an inactive multicast scope
```
PS C:\> Add-DhcpServerv4MulticastScope -ComputerName "DhcpServer01.Contoso.com" -Name "Multicast_AudioConference" -StartRange 224.0.0.0 -EndRange 224.0.0.30 -State Inactive -Ttl 20-LeaseDuration 20
```

This command creates an inactive multicast scope named Multicast_AudioConference on the DHCP server named DhcpServer01.Contoso.com.
The command specifies the lease duration of 20 days for allocating addresses to participants of audio conferences.
You can allocate a single multicast address to multiple clients.
The command specifies that the traffic passes through 20 routers.

### Example 2: Add an active multicast scope
```
PS C:\> Add-DhcpServerv4MulticastScope -ComputerName "DhcpServer01.Contoso.com" -Name "Multicast_VideoConference" -StartRange 224.0.0.50 -EndRange 224.0.0.80
```

This command creates an active multicast scope named Multicast_AudioConference on the DHCP server named DhcpServer01.Contoso.com.
You can use the multicast scope on the DHCP server service for allocating addresses to participants of video conferences.
You can allocate a single multicast address to multiple clients.
The traffic passes through 32 routers, and the lease duration is 30 days.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies the DNS name or IP address of the target computer that runs the DHCP Server service.

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

### -Description
Specifies a description of the multicast scope.
The default value is null.

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

### -EndRange
Specifies the end address of the range for the scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExpiryTime
Specifies the expiry time of the multicast scope.
The default value is infinite.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeaseDuration
Specifies the duration of the IP address lease.
The default value 30 days.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the multicast scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### -StartRange
Specifies the start address of the range of IP addresses for the scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the scope.
The acceptable values for this parameter are:

- Active
- Inactive

The default value is Active.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Active, InActive

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

### -Ttl
Specifies the number of routers through which multicast traffic passes.
The default value is 32.

```yaml
Type: UInt32
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastScope

## NOTES

## RELATED LINKS

[Get-DhcpServerv4MulticastScope](./Get-DhcpServerv4MulticastScope.md)

[Set-DhcpServerv4MulticastScope](./Set-DhcpServerv4MulticastScope.md)

[Remove-DhcpServerv4MulticastScope](./Remove-DhcpServerv4MulticastScope.md)

