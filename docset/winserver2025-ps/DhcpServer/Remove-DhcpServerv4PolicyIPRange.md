---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4PolicyIPRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4policyiprange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4PolicyIPRange
---

# Remove-DhcpServerv4PolicyIPRange

## SYNOPSIS
Deletes an IP range from an existing policy at the scope level.

## SYNTAX

```
Remove-DhcpServerv4PolicyIPRange [-Name] <String> [-ScopeId] <IPAddress> [[-StartRange] <IPAddress>]
 [[-EndRange] <IPAddress>] [-PassThru] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4PolicyIPRange** cmdlet deletes an IP range from an existing policy at the scope level.

If you specify neither the *StartRange* nor the *EndRange* parameter, all of the IP address ranges associated with the policy are deleted.

If you specify only the *StartRange* parameter, the policy IP address range which has the specified starting address is deleted.

If you specify only the *EndRange* parameter, the policy IP address range which has the specified ending address is deleted.

## EXAMPLES

### Example 1: Delete an IP address range from a policy
```
PS C:\> Remove-DhcpServerv4PolicyIPRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -Name "HyperVPolicy" -StartRange 10.10.10.10 -EndRange 10.10.10.20
```

This example deletes the IP address range from 10.10.10.10 through 10.10.10.20 that is associated with the policy named HyperVPolicy in the scope 10.10.10.0.

### Example 2: Delete all IP address ranges from a policy
```
PS C:\> Remove-DhcpServerv4PolicyIPRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -Name "HyperVPolicy"
```

This example deletes all of the IP address ranges associated with the policy named HyperVPolicy in the scope 10.10.10.0.

### Example 3: Delete a range by specifying a start address
```
PS C:\> Remove-DhcpServerv4PolicyIPRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -Name "HyperVPolicy" -StartRange 10.10.10.10
```

This example deletes the IP address range starting from 10.10.10.10 that is associated with the policy named HyperVPolicy in the scope 10.10.10.0.

### Example 4: Delete a range by specifying an end address
```
PS C:\> Remove-DhcpServerv4PolicyIPRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -Name "HyperVPolicy" -EndRange 10.10.10.20
```

This example deletes the IP address range ending at 10.10.10.10 that is associated with the policy named HyperVPolicy in the scope 10.10.10.0.

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
Specifies the ending IP address of the IP address range to delete from the policy.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy for which one or more associated IP address ranges are deleted.

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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, which contains the specified policy.

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

### -StartRange
Specifies the starting IP address of the IP address range to delete from the policy.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4PolicyIPRange
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4PolicyIPRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)

[Get-DhcpServerv4PolicyIPRange](./Get-DhcpServerv4PolicyIPRange.md)

