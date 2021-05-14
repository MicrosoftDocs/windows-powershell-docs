---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://docs.microsoft.com/powershell/module/netwnv/get-netvirtualizationlookuprecord?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetVirtualizationLookupRecord

## SYNOPSIS
Gets policy entries for VMs in a virtual network.

## SYNTAX

```
Get-NetVirtualizationLookupRecord [-AsJob] [-CimSession <CimSession[]>] [-Context <String[]>]
 [-CustomerAddress <String[]>] [-CustomerID <String[]>] [-MACAddress <String[]>] [-ProviderAddress <String[]>]
 [-Rule <RuleType[]>] [-ThrottleLimit <Int32>] [-UseVmMACAddress <Boolean[]>] [-VirtualSubnetID <UInt32[]>]
 [-VMName <String[]>]
```

## DESCRIPTION
The **Get-NetVirtualizationLookupRecord** cmdlet gets lookup record policy entries for IP addresses that belong to a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet gets records that map a Customer Address to a Provider Address.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies an array of medial access control (MAC) addresses that corresponds to the Customer Addresses.

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

### -VirtualSubnetID
Specifies an array of IDs for the virtual subnet that the Customer address belongs to.
The acceptable values for this parameter are:integers from 4096 through 16777214.

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

### -VMName
Specifies an array of names for the VM for a policy entry.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NetVirtualizationLookupRecord](./New-NetVirtualizationLookupRecord.md)

[Remove-NetVirtualizationLookupRecord](./Remove-NetVirtualizationLookupRecord.md)

[Set-NetVirtualizationLookupRecord](./Set-NetVirtualizationLookupRecord.md)

