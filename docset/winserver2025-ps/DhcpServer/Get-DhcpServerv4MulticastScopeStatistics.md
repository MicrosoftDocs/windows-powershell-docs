---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4MulticastScopeStatistics_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4multicastscopestatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4MulticastScopeStatistics
---

# Get-DhcpServerv4MulticastScopeStatistics

## SYNOPSIS
Gets multicast scope statistics.

## SYNTAX

```
Get-DhcpServerv4MulticastScopeStatistics [-ComputerName <String>] [[-Name] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4MulticastScopeStatistics** cmdlet gets multicast scope statistics.
If you do not specify the *Name* parameter, the cmdlet gets statistics for all multicast scopes on the Dynamic Host Configuration Protocol (DHCP) server.

## EXAMPLES

### Example 1: Get multicast scope statistics by using a name
```
PS C:\> Get-DhcpServerv4MulticastScopeStatistics -Name "Multicast_AudioConference" -ComputerName "DhcpServer01.Contoso.com"
```

This command returns the statistics for the multicast scope named Multicast_AudioConference on the DHCP server named DhcpServer01.Contoso.com.

### Example 2: Get statistics for all multicast scopes
```
PS C:\> Get-DhcpServerv4MulticastScopeStatistics -ComputerName "DhcpServer01.Contoso.com"
```

This command returns the statistics for all the multicast scopes on the DHCP server named DhcpServer01.Contoso.com.

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

### -Name
Specifies an array of names of multicast scopes.

```yaml
Type: String[]
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastScopeStatistics[]

## NOTES

## RELATED LINKS

[Get-DhcpServerv4MulticastScope](./Get-DhcpServerv4MulticastScope.md)

