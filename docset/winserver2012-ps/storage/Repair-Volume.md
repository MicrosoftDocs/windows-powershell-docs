---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 41547EC6-C1F1-487F-9BB3-0A08FA80BA70
---

# Repair-Volume

## SYNOPSIS
Performs repairs on a volume.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Repair-Volume [-DriveLetter] <Char[]> [-AsJob] [-CimSession <CimSession[]>] [-OfflineScanAndFix] [-Scan]
 [-SpotFix] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Repair-Volume [-AsJob] [-CimSession <CimSession[]>] [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Repair-Volume [-AsJob] [-CimSession <CimSession[]>] [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-ThrottleLimit <Int32>] -Path <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Repair-Volume [-AsJob] [-CimSession <CimSession[]>] [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-ThrottleLimit <Int32>] -ObjectId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Repair-Volume [-AsJob] [-CimSession <CimSession[]>] [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-ThrottleLimit <Int32>] -FileSystemLabel <String[]> [-Confirm] [-WhatIf]
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

This example scans drive H and reports errors only.

### EXAMPLE 2
```
PS C:\>Repair-Volume -DriveLetter H -OfflineScanAndFix
```

This example takes drive H offline, and fixes all issues.

### EXAMPLE 3
```
PS C:\>Repair-Volume -DriveLetter H -SpotFix
```

This example uses the spot verifier functionality to quickly fix drive H.

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

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the volume to scan based on the file system label (the volume name).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### System.UInt32

## NOTES

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Set-Volume](./Set-Volume.md)

