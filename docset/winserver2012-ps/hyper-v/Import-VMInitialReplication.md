---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/import-vminitialreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-VMInitialReplication

## SYNOPSIS
Imports initial replication files for a Replica virtual machine to complete the initial replication when using external media as the source.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Import-VMInitialReplication [-VMName] <String[]> [-Path] <String> [-AsJob] [-ComputerName <String[]>]
 [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Import-VMInitialReplication [-VM] <VirtualMachine[]> [-Path] <String> [-AsJob] [-PassThru]
```

### UNNAMED_PARAMETER_SET_3
```
Import-VMInitialReplication [-VMReplication] <VMReplication[]> [-Path] <String> [-AsJob] [-PassThru]
```

## DESCRIPTION
The **Import-VMInitialReplication** cmdlet imports initial replication files on a Replica server.
It completes the initial replication of a virtual machine when external is used as the source of the files for initial replication.

## EXAMPLES

### Example 1
```
PS C:\>Import-VMInitialReplication VM01 d:\VMImportLocation\VM01
```

This example imports the initial replication files for a virtual machine named VM01 from location d:\VMImportLocation\VM01.

### Example 2
```
PS C:\>Get-VMReplication | % {$path = "D:\OOBLoc\" + $_.VMName + "_" + $_.VMID; if (Test-Path $path -PathType Container) {Import-VMInitialReplication $_ $path}}
```

This example imports the initial replication files for a set of virtual machines using files located in D:\OOBLoc\

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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
Specifies one or more Hyper-V hosts on which initial replication files are to be imported.
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
Specifies that an object is to be passed through to the pipeline representing the virtual machine for which initial replication files are to be imported.

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

### -Path
Specifies the path of the initial replication files to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the initial replication files are to be imported.

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
Specifies the name of the virtual machine for which the initial replication files are to be imported.

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
Specifies the virtual machine replication object for which initial replication files are to be imported.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



