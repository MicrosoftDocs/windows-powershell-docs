---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://docs.microsoft.com/powershell/module/netwnv/set-netvirtualizationlookuprecord?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetVirtualizationLookupRecord

## SYNOPSIS
Changes settings for policy entries that belong to a virtual network.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetVirtualizationLookupRecord [-AsJob] [-CimSession <CimSession[]>] [-Context <String>]
 [-CustomerAddress <String[]>] [-CustomerID <String>] [-MACAddress <String[]>] [-PassThru]
 [-ProviderAddress <String>] [-Rule <RuleType>] [-ThrottleLimit <Int32>] [-UseVmMACAddress <Boolean>]
 [-VirtualSubnetID <UInt32[]>] [-VMName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetVirtualizationLookupRecord [-AsJob] [-CimSession <CimSession[]>] [-Context <String>]
 [-CustomerID <String>] [-PassThru] [-ProviderAddress <String>] [-Rule <RuleType>] [-ThrottleLimit <Int32>]
 [-UseVmMACAddress <Boolean>] [-VMName <String>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Set-NetVirtualizationLookupRecord** cmdlet changes settings for lookup record policy entries for IP addresses that belong to a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet modifies records that map a Customer Address to a Provider Address.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can update the Provider Address, customer ID, context, VM name, and whether to use a VM media access control (MAC) address.
You can specify which policy entries to update by using a Customer Address, a MAC address, a rule type, or a virtual subnet ID, or you can use the Get-NetVirtualizationLookupRecord cmdlet to obtain a policy entry.

## EXAMPLES

### Example 1: Change context and customer ID
```
PS C:\> Get-NetVirtualizationLookupRecord -VirtualSubnetID 10000 | Set-NetVirtualizationLookupRecord -Context "BlueCustomer Subnet1" -CustomerID "{00000000-0000-0000-0000-000000001234}"
```

This command uses the Get-NetVirtualizationLookupRecord cmdlet to get all the entries with a virtual subnet ID of 10000 and uses the pipe operator to pass them to the Set-NetVirtualizationLookupRecord cmdlet.
This cmdlet changes the context to a descriptive phrase and changes the customer ID to a specified string.

### Example 2: Change Provider Address and virtual subnet ID
```
PS C:\>Set-NetVirtualizationLookupRecord -CustomerAddress "10.0.22.1" -ProviderAddress "172.23.1.1"
```

This command makes changes for the entry that has the Customer Address 10.0.22.1.
It sets the physical address to 172.23.1.1.

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
Specifies an array of IP addresses within the Customer Address network.
You can use both IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MACAddress
Specifies a MAC address that corresponds to the Customer Address.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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
Specifies an IP address, either IPv4 or IPv6, for a physical address that corresponds to the Customer Address.

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

### -UseVmMACAddress
Indicates whether this entry uses its defined MAC address instead of physical MAC address.
Virtual networking can use different MAC addresses for different VMs to balance traffic among multiple CPU cores.

A value of $True is only valid if the **Rule** parameter has a value of TranslationMethodNat.
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
Specifies an array of IDs for virtual subnets that Customer Addresses belongs to.
The acceptable values for this parameter are:integers from 4096 through 16777214.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
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

[New-NetVirtualizationLookupRecord](./New-NetVirtualizationLookupRecord.md)

[Remove-NetVirtualizationLookupRecord](./Remove-NetVirtualizationLookupRecord.md)

