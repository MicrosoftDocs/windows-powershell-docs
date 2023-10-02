---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/restart-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Restart-VM

## SYNOPSIS
Restarts a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Restart-VM [-Name] <String[]> [-AsJob] [-ComputerName <String[]>] [-Force] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Restart-VM [-VM] <VirtualMachine[]> [-AsJob] [-Force] [-Passthru]
```

## DESCRIPTION
The **Restart-VM** cmdlet restarts a virtual machine.
Running this cmdlet results in a "hard" restart, like powering the machine down, then back up again.
This can result in data loss in the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Restart-VM Win7
Confirm
Are you sure you want to restart virtual machine "win7"?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

Performs a hard restart of virtual machine Win7.
This is equivalent to turning off the power to the virtual machine and then restarting it.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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
Specifies one or more Hyper-V hosts on which the virtual machine is to be restarted.
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

### -Force
Specifies that no prompt for confirmation is to appear before the virtual machine is restarted.

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

### -Name
Specifies the name of the virtual machine to be restarted.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be restarted.

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
Specifies the virtual machine to be restarted.

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

## INPUTS

## OUTPUTS

### 
None by default, **Microsoft.HyperV.Powershell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS



