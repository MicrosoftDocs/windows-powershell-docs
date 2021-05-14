---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmremotefx3dvideoadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Adds a RemoteFX video adapter in a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMRemoteFx3dVideoAdapter [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMRemoteFx3dVideoAdapter [-VM] <VirtualMachine[]> [-Passthru]
```

## DESCRIPTION
The **Add-VMRemoteFx3dVideoAdapter** cmdlet adds a RemoteFX video adapter in a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMRemoteFx3dVideoAdapter -VMName Test
```

Adds a RemoteFX video adapter to virtual machine Test.

### Example 2
```
PS C:\>Get-VM Test | Add-VMRemoteFx3dVideoAdapter
```

Adds a RemoteFX video adapter to virtual machine Test.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX video adapter is to be added.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a VMRemoteFxVideoAdapter object is to be passed through to the pipeline representing the RemoteFX video adapter to be added.

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

### -VM
Specifies the virtual machine on which the RemoteFX video adapter is to be added.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of virtual machine on which the RemoteFX video adapter is to be added.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.RemoteFxVideoAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



