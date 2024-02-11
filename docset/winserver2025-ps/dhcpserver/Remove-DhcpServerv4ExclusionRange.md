---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4ExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4exclusionrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4ExclusionRange
---

# Remove-DhcpServerv4ExclusionRange

## SYNOPSIS
Deletes a range of IPv4 addresses that were previously excluded from an IPv4 scope.

## SYNTAX

```
Remove-DhcpServerv4ExclusionRange [-ComputerName <String>] [-ScopeId] <IPAddress> [[-StartRange] <IPAddress>]
 [[-EndRange] <IPAddress>] [-Passthru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4ExclusionRange** cmdlet deletes a range of IPv4 addresses that were previously excluded from an IPv4 scope.
If the *StartRange* and *EndRange* parameters are specified, the exclusion range with the specified starting range and ending range is deleted.
If only the *StartRange* parameter is specified, the exclusion range with specified starting range is deleted.
If only the *EndRange* parameter is specified, the exclusion range with specified ending range is deleted.
If neither the *StartRange* nor the *EndRange* parameter is specified, all exclusion ranges in the specified scope are deleted.

## EXAMPLES

### Example 1: Delete all of the excluded address ranges
```
PS C:\> Remove-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example deletes all of the excluded IPv4 address ranges on the specified DHCP server service.

### Example 2: Delete a specified excluded address range
```
PS C:\> Remove-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -StartRange 10.10.10.1 -EndRange 10.10.10.10
```

This example deletes the excluded IPv4 address range from 10.10.10.1 through 10.10.10.10 from the specified scope on the specified DHCP server service.

### Example 3: Delete an excluded address range that starts with a specified address
```
PS C:\> Remove-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -StartRange 10.10.10.1
```

This example deletes the excluded IPv4 address range starting with IPv4 address 10.10.10.1 from the specified scope on the specified DHCP server service.

### Example 4: Delete an excluded address range that ends with a specified address
```
PS C:\> Remove-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -EndRange 10.10.10.10
```

This example deletes the excluded IPv4 address range ending with IPv4 address 10.10.10.10 from the specified scope on the specified DHCP server service.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the Dynamic Host Configuration Protocol (DHCP) server service.

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
Specifies the ending IPv4 address of the excluded IP range which is to be deleted.

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

### -Passthru
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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, from which the exclusion ranges are to be deleted.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartRange
Specifies the starting IPv4 address of the excluded IP range which is to be deleted.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ExclusionRange
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ExclusionRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4ExclusionRange](./Add-DhcpServerv4ExclusionRange.md)

[Get-DhcpServerv4ExclusionRange](./Get-DhcpServerv4ExclusionRange.md)

