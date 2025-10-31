---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddressSpace.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamaddressspace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamAddressSpace
---

# Add-IpamAddressSpace

## SYNOPSIS
Adds an address space to IPAM.

## SYNTAX

### ProviderAddressSpace (Default)
```
Add-IpamAddressSpace -Name <String> [-ProviderAddressSpace] [-Owner <String>] [-Description <String>]
 [-CustomConfiguration <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomerAddressSpace
```
Add-IpamAddressSpace -Name <String> [-Owner <String>] [-Description <String>] [-CustomConfiguration <String>]
 [-PassThru] [-CustomerAddressSpace] -AssociatedProviderAddressSpace <String> [-Tenant <String>]
 [-VmNetwork <String>] -IsolationMethod <String> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamAddressSpace** cmdlet adds an address space to IP Address Management (IPAM).
A set of connected networks forms an address space.
In IPAM, all IP blocks, IP subnets, IP ranges, and IP addresses in a set of connected networks are grouped in an address space container.
To support network virtualization, IPAM provides two types of address spaces: provider and customer.
By default, all IPAM entities reside in the built-in address space called Default.
Non-virtualized network entities, such as a subnet or an IP address range, reside in the Default address space.

## EXAMPLES

### Example 1: Add a provider address space
```
PS C:\> Add-IpamAddressSpace -Name "ProviderAddSpace01" -ProviderAddressSpace -Description "Provider address space for Contoso"
Name                           : ProviderAddSpace01

Type                           : ProviderAddressSpace

Owner                          :
Description                    : Provider address space for Contoso

AssociatedProviderAddressSpace :
Tenant                         :
VMNetwork                      :
IsolationMethod                :
Ipv4PercentageUtilized         : 0

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command adds a provider address space named ProviderAddSpace01 to IPAM with a description.

### Example 2: Add a customer address space
```
PS C:\> Add-IpamAddressSpace -Name "CustomerAddSpace01" -CustomerAddressSpace -AssociatedProviderAddressSpace "ProviderAddSpace01" -IsolationMethod NVGRE -PassThru
Name                           : CustomerAddSpace01

Type                           : CustomerAddressSpace

Owner                          :

Description                    :

AssociatedProviderAddressSpace : TestProviderAddressSpace

Tenant                         :

VMNetwork                      :

IsolationMethod                : NVGRE

Ipv4PercentageUtilized         : 0

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command adds a customer address space named CustomerAddSpace01 to IPAM.
The command specifies that the provider address space named ProviderAddSpace01 is associated with the customer address space.
The command specifies the Network Virtualization using Generic Routing Encapsulation (NVGRE) network virtualization mechanism for the address space.

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

### -AssociatedProviderAddressSpace
Specifies the provider address space that is associated with the customer address space.
Customer address spaces in IPAM belong to a single provider address space.

```yaml
Type: String
Parameter Sets: CustomerAddressSpace
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CustomConfiguration
Specifies semicolon-separated name/value pairs.
This parameter specifies custom metadata that is associated with the address space.

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

### -CustomerAddressSpace
Indicates that the type of address space that you add is a customer address space.

```yaml
Type: SwitchParameter
Parameter Sets: CustomerAddressSpace
Aliases: CA

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the address space.

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
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: CustomerAddressSpace
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsolationMethod
Specifies the network virtualization mechanism for the address space.
The acceptable values for this parameter are:

- NVGRE
- IPRewrite

```yaml
Type: String
Parameter Sets: CustomerAddressSpace
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the address space.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the owner of the address space.

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

### -ProviderAddressSpace
Indicates that the type of address space that you add is a provider address space.

```yaml
Type: SwitchParameter
Parameter Sets: ProviderAddressSpace
Aliases: PA

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the tenant ID, as a string, that is associated with the customer address space.
You must specify a tenant ID that is compatible with the virtual machine network that you specify for the *VmNetwork* parameter.

```yaml
Type: String
Parameter Sets: CustomerAddressSpace
Aliases:

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

### -VmNetwork
Specifies the name of the virtual machine network for the customer address space.
You must specify a virtual machine network that is associated with the tenant that you specify for the *Tenant* parameter.

```yaml
Type: String
Parameter Sets: CustomerAddressSpace
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

### IpamAddressSpace
This cmdlet returns an object that represents an address space in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamAddressSpace](./Get-IpamAddressSpace.md)

[Set-IpamAddressSpace](./Set-IpamAddressSpace.md)

[Remove-IpamAddressSpace](./Remove-IpamAddressSpace.md)

