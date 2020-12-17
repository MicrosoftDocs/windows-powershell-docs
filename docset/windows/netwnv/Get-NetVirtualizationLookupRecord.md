---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationLookupRecordSettingData.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetVirtualizationLookupRecord
ms.reviewer:
ms.assetid: 33D18FAD-241B-4963-A0DB-A5988F6EFA19
---

# Get-NetVirtualizationLookupRecord

## SYNOPSIS
Gets policy entries for virtual machines in a virtual network.

## SYNTAX

```
Get-NetVirtualizationLookupRecord [-CustomerAddress <String[]>] [-MACAddress <String[]>]
 [-VirtualSubnetID <UInt32[]>] [-ProviderAddress <String[]>] [-CustomerID <String[]>] [-Context <String[]>]
 [-Rule <RuleType[]>] [-VMName <String[]>] [-UseVmMACAddress <Boolean[]>] [-Type <Type[]>]
 [-Unusable <Boolean[]>] [-Unsynchronized <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetVirtualizationLookupRecord** cmdlet gets lookup record policy entries for IP addresses that belong to a Microsoft® Hyper-V® Server 2016 virtual network.
Network Virtualization allows for more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine by using a Customer Address in the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet gets records that map a Customer Address to a Provider Address.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

## EXAMPLES

### Example 1: Get all policy entries for a host
```
PS C:\> Get-NetVirtualizationLookupRecord
```

This command gets all the policy entries for the current host.

### Example 2: Get policy entries for a specified virtual subnet
```
PS C:\>Get-NetVirtualizationLookupRecord -VirtualSubnetID 50002
```

This command gets all policy entries that belong to the virtual subnet that has the ID 50002.

### Example 3: Get policy entries for a physical IP address
```
PS C:\>Get-NetVirtualizationLookupRecord -ProviderAddress "192.168.3.24"
```

This command gets all the policy entries that contain the specified provider address.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -Context
Specifies an array of comments regarding policy entries.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerAddress
Specifies an array of IP addresses in the virtual network.
You can use both IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerID
Specifies an array of IDs for policy entries or virtual machines.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies an array of media access control (MAC) addresses that corresponds to the Customer Addresses.

```yaml
Type: String[]
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 
Accepted values: Static, Dynamic, GatewayWildcard, L2Only

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unsynchronized
Specifies an array of Boolean values that indicates whether this record is not synchronized with the central policy controller.
This is a read-only property of the lookup record that provides diagnostic information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unusable
Specifies an array of Boolean values that indicates whether this record is unusable for data communication.
This is a read-only property of the lookup record that provides diagnostic information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies an array of names for the virtual machine for a policy entry.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualSubnetID
Specifies an array of IDs for the virtual subnet that the Customer address belongs to.
The acceptable values for this parameter are: integers from 4096 through 16777214.

```yaml
Type: UInt32[]
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

## NOTES

## RELATED LINKS

[New-NetVirtualizationLookupRecord](./New-NetVirtualizationLookupRecord.md)

[Remove-NetVirtualizationLookupRecord](./Remove-NetVirtualizationLookupRecord.md)

[Set-NetVirtualizationLookupRecord](./Set-NetVirtualizationLookupRecord.md)

