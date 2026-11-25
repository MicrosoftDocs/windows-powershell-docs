---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamSubnet
---

# Remove-IpamSubnet

## SYNOPSIS
Removes a subnet from IPAM.

## SYNTAX

### Query (cdxml) (Default)
```
Remove-IpamSubnet -NetworkId <String[]> [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-DeleteAssociatedRanges] [-DeleteAssociatedAddresses] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-IpamSubnet -InputObject <CimInstance[]> [-DeleteAssociatedRanges] [-DeleteAssociatedAddresses] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamSubnet** cmdlet removes a given subnet from IP Address Management (IPAM).
By default, the cmdlet returns an error if there are ranges associated with the subnet.
You can use the *DeleteAssociatedRanges* parameter to delete the associated ranges.
You can specify the *DeleteAssociatedAddresses* parameter to delete the associated IP Addresses.

## EXAMPLES

### Example 1 Remove a non-virtualized subnet with a mapped range
```
PS C:\> Remove-IpamSubnet -NetworkId 10.12.0.0/16 -NetworkType NonVirtualized

Confirm

Deleting the non-virtualized subnet Contoso_2 with network 10.12.0.0/16.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

Remove-IpamSubnet : There are ranges associated with this subnet.

At line:1 char:1

+ Remove-IpamSubnet -InputObject $subnet

+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

+ CategoryInfo          : ResourceUnavailable: (MSFT_IPAM_Subnet (InstanceID = "86-2"):ROOT/microsoft/ipam/MSFT_IP

AM_Subnet) [Remove-IpamSubnet], CimException

+ FullyQualifiedErrorId : WIN32 8,Remove-IpamSubnet
```

This command removes a NonVirtualized subnet with a mapped range.
An error occurs because a subnet cannot be deleted if there are ranges mapped to it

### Example 2: Remove a non-virtualized subnet
```
PS C:\> Remove-IpamSubnet -NetworkId 10.12.0.0/16 -NetworkType NonVirtualized -DeleteAssociatedRanges

Confirm

Deleting the non-virtualized subnet Contoso_2 with network 10.12.0.0/16. Ranges mapped to this subnet will also be

deleted.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes a NonVirtualized subnet along with any ranges that are mapped to it.
The cmdlet moves the mapped IP addresses to unmapped address space.

### Example 3: Remove a non-virtualized subnet
```
PS C:\> Remove-IpamSubnet -NetworkId 10.12.0.0/16 -NetworkType NonVirtualized -DeleteAssociatedRanges -DeleteAssociatedAddresses

Confirm

Deleting the non-virtualized subnet Contoso_2 with network 10.12.0.0/16. Ranges mapped to this subnet and IP Addresses

associated via Ranges with this Subnet will also be deleted.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes a NonVirtualized subnet along with ranges that map to it.
Also remove any IP addresses that map to this subnet via the ranges that map to this subnet.

### Example 4: Remove a subnet for a provider network type
```
PS C:\> Remove-IpamSubnet -NetworkId 10.13.0.0/16 -NetworkType Provider -AddressSpace Default -DeleteAssociatedRanges

Confirm

Deleting the fabric subnet Contoso_3 with network 10.13.0.0/16. Ranges mapped to this subnet will also be deleted.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes a subnet for a provider network type from the default address space.

### Example 5: Remove a subnet for a customer network type
```
PS C:\> Remove-IpamSubnet -NetworkId 10.11.8.0/24 -NetworkType Customer -AddressSpace Contoso -DeleteAssociatedRanges

Confirm

Deleting the virtual subnet Contoso_1 with network 10.11.8.0/24. Ranges mapped to this subnet will also be deleted.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes a subnet for a customer network type from the customer address space named Contoso.

## PARAMETERS

### -AddressSpace
Specifies an array of names of address spaces.
If you not specify an address space, the cmdlet removes all address spaces configured in IPAM.

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

### -DeleteAssociatedAddresses
Indicates that the cmdlet deletes the addresses associated with these ranges.

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

### -DeleteAssociatedRanges
Indicates that the cmdlet deletes subnets and any associated ranges.
If you do not specify this parameter, the cmdlet generates an error when there are ranges associated with the subnet.

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

### -NetworkId
Specifies an array of networks for the subnets to remove.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies an array of network types for the subnets to delete.

The acceptable values for this parameter are:

- Provider
 --  Customer
 --  NonVirtualized

  If you do not specify a value, all matching IP subnets of network type Provider, Customer and NonVirtualized will be deleted.

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

### IpamSubnet
This cmdlet returns an object that represents the subnet deleted from the IPAM Server.

## NOTES

## RELATED LINKS

[Add-IpamSubnet](./Add-IpamSubnet.md)

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

