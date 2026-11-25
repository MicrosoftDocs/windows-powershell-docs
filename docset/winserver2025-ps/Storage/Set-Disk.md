---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-disk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Disk
---

# Set-Disk

## SYNOPSIS
Takes a Disk object or unique disk identifiers and a set of attributes, and updates the physical disk on the system.

## SYNTAX

### ByNumberAttributes (Default)
```
Set-Disk [-Number] <UInt32> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-Disk -InputObject <CimInstance[]> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObject
```
Set-Disk -InputObject <CimInstance[]> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectConvertStyle
```
Set-Disk -InputObject <CimInstance[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNumberConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] [-Number] <UInt32> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPathConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] -Path <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIdConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIdAttributes
```
Set-Disk -UniqueId <String> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ById
```
Set-Disk -UniqueId <String> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPathAttributes
```
Set-Disk -Path <String> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPath
```
Set-Disk -Path <String> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByNumber
```
Set-Disk [-Number] <UInt32> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-Disk** cmdlet takes a Disk object or unique disk identifiers and a set of attributes, and updates the physical disk on the system.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-Disk -Number 5 -IsOffline $False
```

This example takes a disk that is offline and makes it online.

### EXAMPLE 2
```
PS C:\>Set-Disk -Number 5 -IsReadonly $False
```

This example takes a disk that is read-only and makes it writeable.

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

### -Guid
Contains a globally unique ID (GUID).

```yaml
Type: String
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
Aliases:

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
Parameter Sets: ByObjectAttributes, ByObject, ByObjectConvertStyle
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsOffline
Specifies that the disk is offline.

```yaml
Type: Boolean
Parameter Sets: ByObject, ById, ByPath, ByNumber
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Sets the disk to be read-only, or read-write (read-only = false).
Note: If the disk is set to read-only, then the disk must be set to read-only = false before using this cmdlet to set the **PartitionStyle** parameter.

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
Specifies a disk number on which the cmdlet acts.

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberConvertStyle, ByNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionStyle
Specifies the type of the partition.
The acceptable values for this parameter are: **MBR** or **GPT**.
The disk must be initialized (such as using the [Initialize-Disk](https://technet.microsoft.com/library/e5369347-7ee0-4cb7-a063-cf1f355d095e) cmdlet) and set to read-write (`IsReadOnly $false`) before this cmdlet will work.
The disk must be set to read-only = false before this cmdlet will work.

```yaml
Type: PartitionStyle
Parameter Sets: ByObjectConvertStyle, ByNumberConvertStyle, ByPathConvertStyle, ByIdConvertStyle
Aliases:
Accepted values: Unknown, MBR, GPT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Contains the device instance path.

```yaml
Type: String
Parameter Sets: ByPathConvertStyle, ByPathAttributes, ByPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Signature
Contains the signature of the disk.

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Type: String
Parameter Sets: ByIdConvertStyle, ByIdAttributes, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Clear-Disk](./Clear-Disk.md)

[Get-Disk](./Get-Disk.md)

[Initialize-Disk](./Initialize-Disk.md)

[Update-Disk](./Update-Disk.md)

