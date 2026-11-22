---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Disk.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/initialize-disk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-Disk
---

# Initialize-Disk

## SYNOPSIS
Initializes a RAW disk for first time use, enabling the disk to be formatted and used to store data.

## SYNTAX

### ByNumber (Default)
```
Initialize-Disk [-Number] <UInt32[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
Initialize-Disk -UniqueId <String[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName
```
Initialize-Disk [-FriendlyName <String[]>] [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPath
```
Initialize-Disk -Path <String[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDisk
```
Initialize-Disk [-VirtualDisk <CimInstance>] [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Initialize-Disk -InputObject <CimInstance[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-Disk** cmdlet initializes a Disk object with the RAW partition style to either the MBR or GPT partition styles.
The default partition style is GPT.
Disks must be initialized before they can be formatted and used to store data.

## EXAMPLES

### Example 1: Initialize a disk using default values
```
PS C:\>Initialize-Disk -Number 1
```

This example initializes the first disk in the computer (disk number 1), using the default values, which initializes the disk using the GPT partition style.

### Example 2: Initialize a disk using the MBR partition style
```
PS C:\> Initialize-Disk -Number 1 -PartitionStyle MBR
```

This example initializes a disk using the MBR partition style.

### Example 3: Initialize a virtual disk
```
PS C:\>Initialize-Disk -VirtualDisk (Get-VirtualDisk -FriendlyName UserData)
```

This example uses the *VirtualDisk* parameter with the **Get-VirtualDisk** cmdlet to get a virtual disk with the friendly name UserData, and initialize the Disk object associated with the virtual disk.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the disk to initialize.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Number
Specifies the disk number of the disk to initialize.

```yaml
Type: UInt32[]
Parameter Sets: ByNumber
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
The disk must be set to read-write (`IsReadOnly $false` ) before this cmdlet will work.

```yaml
Type: PartitionStyle
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, MBR, GPT

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

### -Path
Specifies the path of the disk to initialize.

```yaml
Type: String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the UniqueID of the disk to initialize

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

### -VirtualDisk
Specifies the VirtualDisk object for which you want to initialize the associated Disk object.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the *VirtualDisk* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe an MSFT_Disk object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
If you specify the *Passthru* parameter, this cmdlet returns an object representing the newly initialized disk.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Clear-Disk](./Clear-Disk.md)

[Get-Disk](./Get-Disk.md)

[Get-Partition](./Get-Partition.md)

[Set-Disk](./Set-Disk.md)

[Update-Disk](./Update-Disk.md)

