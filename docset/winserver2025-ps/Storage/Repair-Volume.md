---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Volume.cdxml-help.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/repair-volume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-Volume
---

# Repair-Volume

## SYNOPSIS
Performs repairs on a volume.

## SYNTAX

### ByDriveLetter (Default)
```
Repair-Volume [-DriveLetter] <Char[]> [-OfflineScanAndFix] [-SpotFix] [-Scan] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Repair-Volume -ObjectId <String[]> [-OfflineScanAndFix] [-SpotFix] [-Scan] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPaths
```
Repair-Volume -Path <String[]> [-OfflineScanAndFix] [-SpotFix] [-Scan] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLabel
```
Repair-Volume -FileSystemLabel <String[]> [-OfflineScanAndFix] [-SpotFix] [-Scan] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Repair-Volume -InputObject <CimInstance[]> [-OfflineScanAndFix] [-SpotFix] [-Scan] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-Volume** cmdlet performs repairs on a volume.
The following repair actions are available:

OfflineScanAndFix: Takes the volume offline to scan the volume and fix any errors found (equivalent to `chkdsk /f`).

Scan: Scans the volume without attempting to repair it; all detected corruptions are added to the `$corrupt` system file (equivalent to `chkdsk /scan`).

SpotFix: Takes the volume briefly offline and then fixes only issues that are logged in the `$corrupt` file (equivalent to `chkdsk /spotfix`).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Repair-Volume -DriveLetter H -Scan
```

This example scans the volume H: and reports errors only. It uses the `-DriveLetter` switch to designate the volume by its drive letter and `-Scan` to indicate the scanning action.

### EXAMPLE 2
```
PS C:\>Repair-Volume -DriveLetter GHI -SpotFix
```

This example uses the spot verifier functionality to quickly fix volumes designation G:, H: and I:. It uses the `-DriveLetter` switch to designate multiple volumes by their drive letters and `SpotFix` to indicate the quick fixing action.

### EXAMPLE 3
```
PS C:\> Get-Volume

DriveLetter FriendlyName             FileSystemType DriveType HealthStatus OperationalStatus SizeRemaining      Size
----------- ------------             -------------- --------- ------------ ----------------- -------------      ----
            System Reserved          NTFS           Fixed     Healthy      OK                    178.47 MB    550 MB
C           Contoso - C              NTFS           Fixed     Healthy      OK                     41.28 GB  98.89 GB
                                     NTFS           Fixed     Healthy      OK                     89.03 MB    481 MB
                                     FAT32          Fixed     Healthy      OK                      70.8 MB     96 MB
D           Contoso - D              NTFS           Fixed     Healthy      OK                     29.13 GB  67.68 GB
E           Contoso - E              NTFS           Fixed     Healthy      OK                    148.44 GB 465.76 GB
F           Archives                 NTFS           Fixed     Healthy      OK                    324.13 GB 465.76 GB


PS C:\> Repair-Volume -FileSystemLabel "System Reserved" -OfflineScanAndFix
```

This example takes the System Reserved volume offline, and fixes all issues. This volume has no drive letters assigned to it. The first command, `Get-Volume` gives an overview of the volumes on the local computer. As the output indicates, the volume bearing the "System Reserved" label has no drive letters. Next, the `Repair-Volume` cmdlet uses the `-FileSystemLabel` switch to designate the "System Reserved" volume and the `-OfflineScanAndFix` switch indicates the volume should be taken offline and scanned in full.

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

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the volume to scan based on the file system label (the volume name).

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -ObjectId
Specifies an ID representing the object.
The ID is not globally unique.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OfflineScanAndFix
Performs and offline scan and fix of any errors found in the file system.

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
Contains valid path information.

```yaml
Type: String[]
Parameter Sets: ByPaths
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scan
Scans the volume.

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

### -SpotFix
Takes the volume offline and fixes any issues that are logged in the $corrupt file.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### System.UInt32

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Set-Volume](./Set-Volume.md)
