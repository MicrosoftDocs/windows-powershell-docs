---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Removes a RemoteFX 3D video adapter from a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMRemoteFx3dVideoAdapter [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMRemoteFx3dVideoAdapter [-VM] <VirtualMachine[]> [-Passthru]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMRemoteFx3dVideoAdapter [-VMRemoteFx3dVideoAdapter] <VMRemoteFx3DVideoAdapter[]> [-Passthru]
```

## DESCRIPTION
The **Remove-VMRemoteFx3dVideoAdapter** cmdlet removes a RemoteFX 3D video adapter from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMRemoteFx3dVideoAdapter -VMName TestVM1,TestVM2
```

Removes the RemoteFX adapter from virtual machines TestVM1 and TestVM2.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a RemoteFX 3D video adapter is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMRemoteFxVideoAdapter** object is to be to be passed through to the pipeline representing the RemoteFX 3D video adapter to be removed.

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

### -VMRemoteFx3dVideoAdapter
Specifies the RemoteFX 3D video adapater to be removed.

```yaml
Type: VMRemoteFx3DVideoAdapter[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the RemoteFX 3D video adapter to be removed.

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
Specifies the name of the virtual machine from which the RemoteFX 3D video adapter is to be removed.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### VMRemoteFxVideoAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

