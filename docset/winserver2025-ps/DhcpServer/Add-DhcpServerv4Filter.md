---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Filter_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4filter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4Filter
---

# Add-DhcpServerv4Filter

## SYNOPSIS
Adds a MAC address filter to the DHCP server service.

## SYNTAX

```
Add-DhcpServerv4Filter [-ComputerName <String>] [-Description <String>] [-MacAddress] <String[]>
 [-List] <String> [-Force] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4Filter** cmdlet adds the specified MAC address filter to the Dynamic Host Configuration Protocol (DHCP) server service.
The MAC address can be added to the allow list or the deny list.

## EXAMPLES

### Example 1: Add a client to the allowed filter
```
PS C:\> Add-DhcpServerv4Filter -List Allow -MacAddress "F0-DE-F1-7A-00-5E" -Description "Laptop 09"
```

This example adds the specified client identified by the MAC address to the allowed list of MAC address filters.

### Example 2: Add multiple clients to the allowed filter
```
PS C:\> Add-DhcpServerv4Filter -List Allow -MacAddress "F0-DE-F1-7A-00-5E", "F0-DE-F1-7A-00-5C"
```

This example adds the specified clients identified by their MAC address to the allowed list of MAC address filters.

### Example 3: Add address filters from a file
```
PS C:\> Import-Csv -Path "MacAddressFilters.csv" | Add-DhcpServerv4Filter -ComputerName "dhcpserver.contoso.com" -List Allow
```

This example adds all of the MAC address filters in the file that is named MacAddressFilters.csv to the allow MAC address list of the DHCP server service running on the computer named dhcpserver.contoso.com.
The **Import-Csv** cmdlet returns the objects that have Mac address filter fields that are piped to this cmdlet, which in turn adds the MAC address filters to the server.
The file that is named MacAddressFilters.csv should be in the following comma-separated values (CSV) format:

`MacAddress,Description`

`1a-1b-1c-1d-1e-1f,Computer1`

`2a-2b-2c-2d-2e-2f,Computer2`

`3a-3b-3c-3d-3e-3f,Computer3`

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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
Specifies the description string for the MAC address filter being added.

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

### -Force
Specifies that, if one or more of the MAC addresses are already present in the allow or deny list, the matching MAC addresses are deleted and the new entries created.

This parameter is useful in the case where the MAC address specified is already present in one list, such as the allow list, and the same MAC address now has to be added to the other list, such as the deny list.

If this parameter is not specified, the cmdlet fails if the specified MAC address is already present in any of the lists.

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

### -List
Specifies the list to which one or more MAC addresses are to be added.
The acceptable values for this parameter are: Allow or Deny.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Allow, Deny

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MacAddress
Specifies one or more MAC addresses which are to be added to the MAC address filter list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ClientId

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Filter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Filter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4Filter](./Get-DhcpServerv4Filter.md)

[Get-DhcpServerv4FilterList](./Get-DhcpServerv4FilterList.md)

[Get-DhcpServerv4Lease](./Get-DhcpServerv4Lease.md)

[Remove-DhcpServerv4Filter](./Remove-DhcpServerv4Filter.md)

[Set-DhcpServerv4FilterList](./Set-DhcpServerv4FilterList.md)

