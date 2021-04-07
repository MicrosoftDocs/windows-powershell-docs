---
author: Kateyanne
description: 
external help file: MSFT_NetVirtualizationLookupRecordSettingData.cdxml-help.xml
manager: jasgro
Module Name: NetWNV
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/netwnv/remove-netvirtualizationlookuprecord?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetVirtualizationLookupRecord
---

# Remove-NetVirtualizationLookupRecord

## SYNOPSIS
Removes policy entries for IP addresses in a virtual network.

## SYNTAX

### ByName (Default)
```
Remove-NetVirtualizationLookupRecord [-CustomerAddress <String[]>] [-MACAddress <String[]>]
 [-VirtualSubnetID <UInt32[]>] [-ProviderAddress <String[]>] [-CustomerID <String[]>] [-Context <String[]>]
 [-Rule <RuleType[]>] [-VMName <String[]>] [-UseVmMACAddress <Boolean[]>] [-Type <Type[]>]
 [-Unusable <Boolean[]>] [-Unsynchronized <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetVirtualizationLookupRecord -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetVirtualizationLookupRecord** cmdlet removes lookup record policy entries for IP addresses that belong to a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet removes records that map a Customer Address to a Provider Address.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify which entries to remove, or you can remove all policy entries for a hv_win8_2 host.
You can use the Get-NetVirtualizationLookupRecord cmdlet to get entries to remove.

## EXAMPLES

### Example 1: Remove all policy entries
```
PS C:\> Remove-NetVirtualizationLookupRecord
```

This command removes all the policy entries for the current host.

### Example 2: Remove policy entries for a specified virtual subnet
```
PS C:\>Remove-NetVirtualizationLookupRecord -VirtualSubnetID 10234
```

This command removes all policy entries that belong to the virtual subnet that has the ID 10234.

### Example 3: Remove policy entries for a specified VM name
```
PS C:\>Remove-NetVirtualizationLookupRecord -VMName "Contoso-VM2"
```

This command removes all the policy entries that contain the specified VM name.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Context
Specifies an array of comments regarding policy entries.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerAddress
Specifies an array of IP addresses within the virtual network.
You can use both IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerID
Specifies an array of IDs for policy entries or VMs.

```yaml
Type: String[]
Parameter Sets: ByName
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

### -MACAddress
Specifies an array of media access control (MAC) addresses that corresponds to the Customer Addresses.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -ProviderAddress
Specifies an array of IP addresses, either IPv4 or IPv6, for physical addresses that corresponds to the Customer Addresses.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies an array of virtualization mechanisms that policy entries use.
The acceptable values for this parameter are:

- TranslationMethodNat.
IP address rewrite.
- TranslationMethodEncap.
Network Virtualization Generic Routing Encapsulation (NVGRE).
- TranslationMethodNone.
None.

```yaml
Type: RuleType[]
Parameter Sets: ByName
Aliases: 
Accepted values: TranslationMethodNat, TranslationMethodEncap, TranslationMethodNone

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

### -Type
Specifies an array of types.
The type determines the address mapping for a record.

```yaml
Type: Type[]
Parameter Sets: ByName
Aliases: 
Accepted values: Static, Dynamic, GatewayWildcard, L2Only

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unsynchronized
Specifies an array of Boolean values that indicate whether a record is not synchronized with the central policy controller.

```yaml
Type: Boolean[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unusable
Specifies an array of Boolean values that indicate whether a record is unusable for data communication.

```yaml
Type: Boolean[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseVmMACAddress
Specifies an array of Boolean values that indicate whether an entry uses its defined MAC address instead of physical MAC address.

```yaml
Type: Boolean[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies an array of names for the VM for a policy entry.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualSubnetID
Specifies an array of IDs for the virtual subnet that the Customer address belongs to.
The acceptable values for this parameter are:integers from 4096 through 16777214.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationLookupRecord](./Get-NetVirtualizationLookupRecord.md)

[New-NetVirtualizationLookupRecord](./New-NetVirtualizationLookupRecord.md)

[Set-NetVirtualizationLookupRecord](./Set-NetVirtualizationLookupRecord.md)

