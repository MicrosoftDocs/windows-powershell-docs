---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/disable-physicaldiskindication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-PhysicalDiskIndication

## SYNOPSIS
Turns off the identification LED on the specified physical disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-PhysicalDiskIndication [-FriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-PhysicalDiskIndication [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -UniqueId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-PhysicalDiskIndication [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-PhysicalDiskIndication** cmdlet turns off the identification LED on the specified physical disk.
The LED is typically used for visual identification of the location of a physical disk in an enclosure for removal and replacement operations.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Disable the identification LED on all physical disks in a pool
```
PS C:\>$stpool = (Get-StoragePool -FriendlyName "SpacePool")



PS C:\>Disable-PhysicalDiskIndication -StoragePool $stpool
```

This example assigns the storage pool named SpacePool to the $stpool variable, and then uses this cmdlet to disable the identification LED on all disks in the storage pool referenced by the $stpool variable, SpacePool.

### Example 2: Disable the identification LED on all physical disks used by a virtual disk
```
PS C:\>$vdisk = (Get-VirtualDisk -FriendlyName "Bruce's Music")



PS C:\>Disable-PhysicalDiskIndication -VirtualDisk $vdisk
```

This example assign the virtual disk named Bruce's Music to the $vdisk variable, and then uses this cmdlet to disable the identification LED on the virtual disk referenced by the $vdisk variable,

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

### -FriendlyName
Specifies the friendly name of the disk on which to turn off the identification LED.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the PhysicalDisk object on which to turn off the identification LED.
Enter a PhysicalDisk CIM object, which you can get by using the Get-PhysicalDisk cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing physical disk.
By default, this cmdlet does not generate any output.

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
Specifies the UniqueID of the disk on which to turn off the identification LED.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe a Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet outputs an object that represents the physical disk for which you disabled the identification LED.

## NOTES

## RELATED LINKS

[Enable-PhysicalDiskIndication](./Enable-PhysicalDiskIndication.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

