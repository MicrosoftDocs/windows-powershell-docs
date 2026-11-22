---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ResiliencySetting.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-resiliencysetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ResiliencySetting
---

# Set-ResiliencySetting

## SYNOPSIS
Modifies the properties of the specified resiliency setting name.

## SYNTAX

### ByName (Default)
```
Set-ResiliencySetting -Name <String[]> -StoragePool <CimInstance> [-NumberOfDataCopiesDefault <UInt16>]
 [-PhysicalDiskRedundancyDefault <UInt16>] [-NumberOfColumnsDefault <UInt16>] [-AutoNumberOfColumns]
 [-InterleaveDefault <UInt64>] [-NumberOfGroupsDefault <UInt16>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Set-ResiliencySetting -UniqueId <String[]> [-NumberOfDataCopiesDefault <UInt16>]
 [-PhysicalDiskRedundancyDefault <UInt16>] [-NumberOfColumnsDefault <UInt16>] [-AutoNumberOfColumns]
 [-InterleaveDefault <UInt64>] [-NumberOfGroupsDefault <UInt16>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-ResiliencySetting -InputObject <CimInstance[]> [-NumberOfDataCopiesDefault <UInt16>]
 [-PhysicalDiskRedundancyDefault <UInt16>] [-NumberOfColumnsDefault <UInt16>] [-AutoNumberOfColumns]
 [-InterleaveDefault <UInt64>] [-NumberOfGroupsDefault <UInt16>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ResiliencySetting** cmdlet modifies the properties of the specified resiliency setting name.
For example, the user can specify that when creating any new virtual disk using the resiliency setting named Mirror, that the default interleave value would be 128K, or to define the default number of columns to use when creating a Simple (stripe without parity) virtual disk.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-ResiliencySetting -Name "Mirror" -StoragePool (Get-StoragePool -FriendlyName "CompanyData") -NumberofColumnsDefault 8 -NumberofDataCopies 2
```

This example sets the default number of columns to eight on virtual disks that use the Mirror setting, with the number of data copies set to two, indicating a two-way mirror, instead of a three-way mirror.
The command uses the Get-StoragePool cmdlet to obtain the storage pool that has the friendly name CompanyData as a value for the *StoragePool* parameter.
A two-way mirror with eight columns requires 16 physical disks to create.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Indicates whether the provider automatically determines the best possible column count for a resiliency setting on a storage pool.
The value ranges are:

- Mirror.
The minimum is two for two-way mirror or three for three-way mirror.
The maximum is eight times the number of data copies.
- Parity.
The minimum is three for single parity and seven for dual parity.
The maximum is eight for single parity and 17 for dual parity.
- Simple.
The minimum is one.
The maximum is eight.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterleaveDefault
Specifies the default interleave value to use.
The interleave value represents the number of bytes that is written to a single physical disk.
Therefore, `Interleave * NumberOfColumns` yields the size of one stripe of user data.

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
Parameter Sets: ByName
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

### -NumberOfGroupsDefault
Specifies the default number of groups used by Local Reconstruction Coding (LRC) with a dual parity virtual disk.
We recommend omitting this parameter and using the defaults.

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
The Storage Pool CIM object is exposed by the [Get-StoragePool](https://technet.microsoft.com/library/288acad9-7678-45c2-b7b4-3a0522fea499) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByName
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
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
You can use the pipeline operator to pass an MSFT_ResiliencySetting object to the *InputObject* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the *StoragePool* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
This cmdlet generates an object that represents resiliency settings if you specify the *PassThru* parameter.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-ResiliencySetting](./Get-ResiliencySetting.md)

[Get-StoragePool](./Get-StoragePool.md)

