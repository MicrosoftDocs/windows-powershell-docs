---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4MulticastExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4multicastexclusionrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4MulticastExclusionRange
---

# Get-DhcpServerv4MulticastExclusionRange

## SYNOPSIS
Retrieves the exclusion range for a specified multicast scope.

## SYNTAX

```
Get-DhcpServerv4MulticastExclusionRange [-ComputerName <String>] [[-Name] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4MulticastExclusionRange** cmdlet retrieves the exclusion range for a specified multicast scope.
An exclusion prevents the Dynamic Host Configuration Protocol (DHCP) Server service from offering these addresses for DHCP assignment.

## EXAMPLES

### Example 1: Retrieve exclusion range for a scope
```
PS C:\> Get-DhcpServerv4MulticastExclusionRange -ComputerName "DhcpServer01.Contoso.com" -Name "Multicast_AudioConference"
```

This command retrieves the exclusion ranges for the multicast scope Multicast_AudioConference.

### Example 2: Retrieve exclusion ranges for all multicast scopes
```
PS C:\> Get-DhcpServerv4MulticastExclusionRange -ComputerName "DhcpServer01.Contoso.com"
```

This command returns the exclusion ranges for all multicast scopes on the computer named DhcpServer01.Contoso.com.

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
Specifies an array of names of multicast scopes from which to remove an exclusion range.

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

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastExclusionRange[]

## NOTES

## RELATED LINKS

[Add-DhcpServerv4MulticastExclusionRange](./Add-DhcpServerv4MulticastExclusionRange.md)

[Remove-DhcpServerv4MulticastExclusionRange](./Remove-DhcpServerv4MulticastExclusionRange.md)

