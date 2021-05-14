---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmremotefx3dvideoadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Configures the RemoteFX 3D video adapter of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMRemoteFx3dVideoAdapter [-VMName] <String[]> [[-MonitorCount] <Byte>] [[-MaximumResolution] <String>]
 [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMRemoteFx3dVideoAdapter [-VM] <VirtualMachine[]> [[-MonitorCount] <Byte>] [[-MaximumResolution] <String>]
 [-Passthru]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMRemoteFx3dVideoAdapter [-VMRemoteFx3dVideoAdapter] <VMRemoteFx3DVideoAdapter[]> [[-MonitorCount] <Byte>]
 [[-MaximumResolution] <String>] [-Passthru]
```

## DESCRIPTION
The **Set-VMRemoteFx3dVideoAdapter** cmdlet configures the RemoteFX 3D video adapter of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMRemoteFx3dVideoAdapter -VMName TestVM -MaximumResolution 1920x1200
```

Sets the maximum resolution of the RemoteFX adapter on virtual machine TestVM to 1920x1200.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX 3D video adapter is to be configured.
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

### -MaximumResolution
Specifies the maximum resolution supported by this adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -MonitorCount
Specifies the maximum number of monitors supported by this adapter.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.RemoteFxVideoAdapter** object is to be passed through to the pipeline representing the adapter to be configured.

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
Specifies the virtual machine on which the adapter is to be configured.

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
Specifies the name of the virtual machine on which the adapter is to be configured.

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

### -VMRemoteFx3dVideoAdapter
Specifies the adapter to be configured.

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

## INPUTS

## OUTPUTS

### 
None by default; Microsoft.Virtualization.Powershell.RemoteFxVideoAdapter if **-PassThru** is specified.

## NOTES

## RELATED LINKS



