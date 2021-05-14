---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/stop-vminitialreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-VMInitialReplication

## SYNOPSIS
Stops an ongoing initial replication.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-VMInitialReplication [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-VMInitialReplication [-VM] <VirtualMachine[]> [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Stop-VMInitialReplication [-VMReplication] <VMReplication[]> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-VMInitialReplication** cmdlet stops an ongoing initial replication that uses either a virtual machine restored from backup or the network.
It does not stop an initial replication that uses external media.
For an initial replication that uses external media, you can use this cmdlet to stop the export, which returns the virtual machine to a pending state.
After an export is finished, the initial replication cannot be stopped.

## EXAMPLES

### Example 1
```
PS C:\> Stop-VMInitialReplication VM01
```

This example stops initial replication of a virtual machine named VM01.

### Example 2
```
PS C:\>Stop-VMInitialReplication *
```

This example stops initial replication of all virtual machines whose initial replication is in progress on the local Replica server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which an ongoing initial replication is to be stopped.
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

### -PassThru
Specifies that an object is to be passed through to the pipeline representing the virtual machine whose initial replication is to be stopped.

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
Specifies the virtual machine whose initial replication is to be stopped.

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
Specifies the name of the virtual machine whose initial replication is to be stopped.

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

### -VMReplication
Specifies the virtual machine replication to be stopped.

```yaml
Type: VMReplication[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



