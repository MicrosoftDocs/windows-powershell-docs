---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamRange
---

# Remove-IpamRange

## SYNOPSIS
Removes a range of IP addresses from an IPAM server configuration.

## SYNTAX

### Query (cdxml) (Default)
```
Remove-IpamRange [-StartIPAddress] <IPAddress[]> [-EndIPAddress] <IPAddress[]> [-ManagedByService <String[]>]
 [-ServiceInstance <String[]>] [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-DeleteMappedAddresses] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-IpamRange -InputObject <CimInstance[]> [-DeleteMappedAddresses] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamRange** cmdlet removes a given range of IP addresses from an IP Address Management (IPAM) server configuration.
You can choose to delete the addresses that map to this range or to retain them.

## EXAMPLES

### Example 1: Remove an IP address range
```
PS C:\> Get-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254|Remove-IpamRange
Confirm

This will permanently delete the given IP Range from IPAM. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes an IP address range without deleting the mapped IP addresses.
The mapped addresses are marked as unmapped and moved to unmapped address space.

### Example 2: Remove an IP address range and mapped IP addresses
```
PS C:\> Get-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254|Remove-IpamRange -DeleteMappedAddresses
Confirm

Deleting the range with start IP address 10.12.3.1 and end IP address 10.12.3.254 managed by localhost instance of IPAM. Any addresses mapped to this range will be deleted. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes an IP address range and the corresponding mapped IP addresses.

### Example 3: Remove an IP address range for an address space
```
PS C:\> Get-IpamRange -StartIPAddress 10.20.4.1 -EndIPAddress 10.20.4.99 -ManagedByService IPAM -ServiceInstance Localhost -Customer -CustomerAddressSpace Contoso | Remove-IpamRange -DeleteMappedAddresses
Confirm

This will permanently delete the given IP Range from IPAM. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes the customer IP addresses range by using the *StartIPAddress* and *EndIPAddress* parameters in the customer address space named Contoso

## PARAMETERS

### -AddressSpace
Specifies an array of the IP address ranges to delete.
If you do not specify a value, the cmdlet removes data for all NonVirtualized, Provider and Customer address spaces in IPAM.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DeleteMappedAddresses
Indicates that the cmdlet deletes the IP addresses that map to an IP range, rather than retain them.

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

### -EndIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the high end of the range to remove.

```yaml
Type: IPAddress[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagedByService
Specifies an array of services that manage the range to remove.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: MB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies an array of network types for the addresses to remove.

The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

If you do not specify a value, the cmdlet deletes all matching IP address ranges of network type Provider, Customer, and NonVirtualized.

```yaml
Type: VirtualizationType[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
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

### -ServiceInstance
Specifies an array of service instances that manage the address ranges to remove.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: SI

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the low end of the range to remove.

```yaml
Type: IPAddress[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
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

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Range[]
This cmdlet returns an object that represents IP address range objects deleted from IPAM.

## NOTES

## RELATED LINKS

[Add-IpamRange](./Add-IpamRange.md)

[Export-IpamRange](./Export-IpamRange.md)

[Get-IpamRange](./Get-IpamRange.md)

[Import-IpamRange](./Import-IpamRange.md)

[Set-IpamRange](./Set-IpamRange.md)

