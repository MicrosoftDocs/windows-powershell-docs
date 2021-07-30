---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://docs.microsoft.com/powershell/module/netwnv/new-netvirtualizationlookuprecord?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetVirtualizationLookupRecord

## SYNOPSIS
Creates a policy entry for an IP address in a virtual network.

## SYNTAX

```
New-NetVirtualizationLookupRecord [-AsJob] [-CimSession <CimSession[]>] [-Context <String>]
 [-CustomerID <String>] [-ThrottleLimit <Int32>] [-UseVmMACAddress <Boolean>] [-VMName <String>]
 -CustomerAddress <String> -MACAddress <String> -ProviderAddress <String> -Rule <RuleType>
 -VirtualSubnetID <UInt32>
```

## DESCRIPTION
The **New-NetVirtualizationLookupRecord** cmdlet creates a lookup record policy entry for an IP address that belongs to a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet creates a record that maps a Customer Address to a Provider Address.
For more information, see Network Virtualization technical detailshttps://technet.microsoft.com/library/jj134174.aspx (https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

To create a policy entry, you must specify a Customer Address, a VM media access control (MAC) address, a Provider Address, a rule type, and a virtual subnet ID.
You can also specify a context, a customer ID, and a VM name, as well as whether to use a VM virtual MAC address.

## EXAMPLES

### Example 1: Create a policy entry
```
PS C:\> New-NetVirtualizationLookupRecord -CustomerAddress "10.0.0.5" -MACAddress "101010101105" -ProviderAddress "192.168.1.101" -Rule "TranslationMethodEncap" -VirtualSubnetID "6000" -VMName "BlueS1-VM1"
```

This command creates a policy entry for a Customer Address 10.0.0.5.
The command specifies the required values: a MAC address for the VM, the physical Provider Address, a rule type (TranslationMethodEncap, which means the entry uses NVGRE), and a virtual subnet ID.
The command also specifies a name for the VM.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies a comment regarding the policy entry.
Administrators can use this comment for any purpose.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerAddress
Specifies the IP address for a VM.
You can use can use either an IPv4 or IPv6 address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomerID
Specifies an ID for a policy entry or VM.
Administrators can use this setting for any purpose.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies a MAC address that corresponds to the Customer Address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderAddress
Specifies an IP address, either IPv4 or IPv6, for a physical address that corresponds to the Customer Address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies which type of virtualization mechanism that the policy entry uses.
The acceptable values for this parameter are:

- TranslationMethodNat.
IP address rewrite.
- TranslationMethodEncap.
Network Virtualization Generic Routing Encapsulation (NVGRE).
- TranslationMethodNone.
None.

```yaml
Type: RuleType
Parameter Sets: (All)
Aliases: 

Required: True
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

### -UseVmMACAddress
Indicates whether this entry uses its defined MAC address instead of physical MAC address.
Virtual networking can use different MAC addresses for different VMs to balance traffic among multiple CPU cores.

A value of $True is valid only if the **Rule** parameter has a value of TranslationMethodNat.
The default value for this setting is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualSubnetID
Specifies an ID for the virtual subnet that the Customer address belongs to.
The acceptable values for this parameter are:integers from 4096 through 16777214.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies a name for the VM for this policy entry.
Administrators can use this name for any purpose.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationLookupRecord](./Get-NetVirtualizationLookupRecord.md)

[Remove-NetVirtualizationLookupRecord](./Remove-NetVirtualizationLookupRecord.md)

[Set-NetVirtualizationLookupRecord](./Set-NetVirtualizationLookupRecord.md)

