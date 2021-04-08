---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/set-resiliencysetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ResiliencySetting

## SYNOPSIS
Modifies the properties of the specified resiliency setting name.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-ResiliencySetting [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>]
 [-InterleaveDefault <UInt64>] [-NumberOfColumnsDefault <UInt16>] [-NumberOfDataCopiesDefault <UInt16>]
 [-PassThru] [-PhysicalDiskRedundancyDefault <UInt16>] [-ThrottleLimit <Int32>] -Name <String[]>
 -StoragePool <CimInstance>
```

### UNNAMED_PARAMETER_SET_2
```
Set-ResiliencySetting [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>]
 [-InterleaveDefault <UInt64>] [-NumberOfColumnsDefault <UInt16>] [-NumberOfDataCopiesDefault <UInt16>]
 [-PassThru] [-PhysicalDiskRedundancyDefault <UInt16>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
Set-ResiliencySetting [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>]
 [-InterleaveDefault <UInt64>] [-NumberOfColumnsDefault <UInt16>] [-NumberOfDataCopiesDefault <UInt16>]
 [-PassThru] [-PhysicalDiskRedundancyDefault <UInt16>] [-ThrottleLimit <Int32>] -UniqueId <String[]>
```

## DESCRIPTION
The **Set-ResiliencySetting** cmdlet modifies the properties of the specified resiliency setting name.
For example, the user can specify that when creating any new virtual disk using the resiliency setting named Mirror, that the default interleave value would be 128K, or to define the default number of columns to use when creating a Simple (stripe without parity) virtual disk.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-ResiliencySetting -Name "Mirror" -NumberofColumnsDefault 8 -NumberofDataCopies 2
```

This example sets the default number of columns to eight on virtual disks that use the Mirror setting, with the number of data copies set to two, indicating a two-way mirror, instead of a three-way mirror.
A two-way mirror with eight columns requires 16 physical disks to create.

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

### -AutoNumberOfColumns


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

### -InputObject
Accepts an object from the pipeline as input.

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

### -InterleaveDefault
Specifies the default interleave value to use.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of an object or setting.
The acceptable values for this parameter are:simple, mirror, or parity.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumnsDefault
Specifies the default number of columns to create.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfDataCopiesDefault
Specifies the default number of data copies to create.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 


                        
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -PhysicalDiskRedundancyDefault
Specifies the default number to use for the physical disk redundancy value.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Accepts a StoragePool object as input.
The Storage Pool CIM object is exposed by the Get-StoragePoolhttp://technet.microsoft.com/library/288acad9-7678-45c2-b7b4-3a0522fea499 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UniqueId
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-ResiliencySetting](./Get-ResiliencySetting.md)

