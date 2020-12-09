---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Restore-VMSnapshot

## SYNOPSIS
Restores a virtual machine snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Restore-VMSnapshot [-Name] <String> [-VMName] <String> [-AsJob] [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Restore-VMSnapshot [-VM] <VirtualMachine> [-AsJob] [-Passthru] [-Name] <String>
```

### UNNAMED_PARAMETER_SET_3
```
Restore-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-AsJob] [-Passthru]
```

## DESCRIPTION
The **Restore-VMSnapshot** cmdlet restores a virtual machine snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Restore-VMSnapshot -Name 'Base image' -VMName TestVM
Confirm
Are you sure you want to perform this action?
Restore-VMSnapshot will restore snapshot "Base image".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"): Y
```

Restores snapshot Base image of virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM | Foreach-Object { $_ | Get-VMSnapshot | Sort CreationTime | Select -Last 1 | Restore-VMSnapshot -Confirm:$false }
```

Applies the most recent snapshot on all virtual machines with no confirmation prompts.

## PARAMETERS

### -AsJob
Specified that the cmdlet is to be run as a background job.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine snapshot is to be restored. 
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

### -Name
Specifies the name of the snapshot to be restored.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Passthru
Specifies that a **VMSnapshot** is to be passed through to the pipeline representing the snapshot to be restored.

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
Specifies the virtual machine to be restored.

```yaml
Type: VirtualMachine
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to be restored.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMSnapshot
```yaml
Type: VMSnapshot[]
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

### None
Default

### VMSnapshot
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



