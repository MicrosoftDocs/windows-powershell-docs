---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapteracl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMNetworkAdapterAcl

## SYNOPSIS
Gets the ACLs configured for a virtual machine network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMNetworkAdapterAcl [[-VMName] <String[]>] [-ComputerName <String[]>] [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMNetworkAdapterAcl [-ComputerName <String[]>] [-VMNetworkAdapterName <String>] [-ManagementOS]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMNetworkAdapterAcl [-VM] <VirtualMachine[]> [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMNetworkAdapterAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMNetworkAdapterAcl [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
The **Get-VMNetworkAdapterAcl** cmdlet gets the ACLs configured for a virtual machine network adapter.
If an ACL entry is created to be applied to both directions, it will appear under the list of entries for the inbound direction and under the list of entries for the outbound direction in the output from Get-VMNetworkAdapterAcl.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMNetworkAdapterAcl -VMName Redmond
```

Gets all the port ACLs configured on virtual machine Redmond.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the ACLs configured for a virtual machine network adapter are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the ACLs are to be configured in the management (i.e.
the parent, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter for which the configured ACLs are to be retrieved.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the virtual network adapter name for which the configured ACLs are to be retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



