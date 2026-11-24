---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4MulticastExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4multicastexclusionrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4MulticastExclusionRange
---

# Remove-DhcpServerv4MulticastExclusionRange

## SYNOPSIS
Removes a range of addresses previously excluded from a multicast scope.

## SYNTAX

```
Remove-DhcpServerv4MulticastExclusionRange [-ComputerName <String>] [[-EndRange] <IPAddress>] [-Name] <String>
 [[-StartRange] <IPAddress>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4MulticastExclusionRange** cmdlet removes a range of addresses previously excluded from a multicast scope.
The addresses are available immediately after the cmdlet runs.
An exclusion prevents the Dynamic Host Configuration Protocol (DHCP) Server service from offering these addresses for DHCP assignment.

## EXAMPLES

### Example 1: Remove an excluded address range by scope name
```
PS C:\> Remove-DhcpServerv4MulticastExclusionRange -Name "Multicast_VideoConference" -ComputerName "DhcpServer01.Contoso.com"
```

This command removes all excluded multicast IP address ranges from the multicast scope named Multicast_VideoConference from the DHCP Server service that runs on the computer named DhcpServer01.Contoso.com.

### Example 2: Remove an excluded address range by IP address
```
PS C:\> Remove-DhcpServerv4MulticastExclusionRange -Name "Multicast_VideoConference" -StartRange 224.0.0.21 -EndRange 224.0.0.25 -ComputerName "DhcpServer01.Contoso.com"
```

This command removes the excluded multicast IP address range 224.0.0.21 through 224.0.0.25 from the multicast scope named Multicast_VideoConference.

### Example 3: Remove an excluded address range by start range
```
PS C:\> Remove-DhcpServerv4MulticastExclusionRange -Name "Multicast_VideoConference" -StartRange 224.0.0.21 -ComputerName "DhcpServer01.Contoso.com"
```

This command removes the excluded multicast IP address range starting with address 224.0.0.21.
The command specifies the multicast scope named Multicast_VideoConference for the DHCP Server service that runs on the computer named DhcpServer01.Contoso.com.

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
Specifies the Domain Name System (DNS) name or IP address of the target computer that runs the DHCP Server service.

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

### -EndRange
Specifies the high end of the range of IP addresses previously excluded from the scope.
Use the *StartRange* parameter to specify the low end of the range of IP addresses to remove from the exclusion range.
If you do not specify the low end of the range by using the *StartRange* parameter, the cmdlet removes the exclusion range that ends with this parameter.
If the DHCP Server service is not excluding addresses ending at the specified value, the cmdlet returns an error and exits.

If you do not specify either the low end or the high end of the exclusion range, the cmdlet removes all exclusion ranges for the specified scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the multicast scope from which to remove the IP address exclusion range.

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
Passthru If this parameter is specified, the cmdlet return the PowerShell objects which are deleted.

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
Specifies the low end of the range of IP addresses that were previously excluded from the scope.
Use the *EndRange* parameter to specify the high end of the range of IP addresses to remove from the exclusion range.
If you do not specify the high end of the range by using the *EndRange* parameter, the cmdlet removes the exclusion range that starts with this parameter.
If the DHCP Server service is not excluding addresses starting at the specified value, the cmdlet returns an error and exits.

If you do not specify either the low end or the high end of the exclusion range, the cmdlet removes all exclusion ranges for the specified scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastExclusionRange[]

## NOTES

## RELATED LINKS

[Add-DhcpServerv4MulticastExclusionRange](./Add-DhcpServerv4MulticastExclusionRange.md)

[Get-DhcpServerv4MulticastExclusionRange](./Get-DhcpServerv4MulticastExclusionRange.md)

