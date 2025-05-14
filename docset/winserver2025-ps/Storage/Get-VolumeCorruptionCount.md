---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Volume.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-volumecorruptioncount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VolumeCorruptionCount
---

# Get-VolumeCorruptionCount

## SYNOPSIS
Gets a count of the file system errors on the NTFS volume.

## SYNTAX

### ByDriveLetter (Default)
```
Get-VolumeCorruptionCount [-DriveLetter] <Char[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ById
```
Get-VolumeCorruptionCount -ObjectId <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPaths
```
Get-VolumeCorruptionCount -Path <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByLabel
```
Get-VolumeCorruptionCount -FileSystemLabel <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-VolumeCorruptionCount -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VolumeCorruptionCount** cmdlet gets a count of the file system errors on the NTFS volume.
Chkdsk scans a volume for file system errors and stores the result as metadata.
This cmdlet enumerates the list of errors on the volume and returns a count of the errors.
If you specify the **Verbose** parameter, the cmdlet also generates a description for each error.

## EXAMPLES

### Example 1: Get the volume corruption count
```
PS C:\>Get-VolumeCorruptionCount -Verbose C
VERBOSE: Corruption Record: 000000000000000000
VERBOSE: Header:
VERBOSE: Version        : 1.0
VERBOSE: Flags          : (0x000000000000002c) GLOBALLY_VERIFIED | SKIP_SELF_HEALING | TESTED_DUPLICATE
VERBOSE: Length         : 188 bytes
VERBOSE: InstanceTag    : {00000000-0000-0000-0000-000000000000}
VERBOSE: description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
VERBOSE: Verb           : IndexEntry
VERBOSE: Length         : 164 bytes
VERBOSE: Verb-Specific Fields:
VERBOSE: Index          :
VERBOSE: FRN            : 0x0001 0000`00000023
VERBOSE: Attribute:
VERBOSE: TypeCode: 0 Name: $I30
VERBOSE: Value Length   : 132 bytes
VERBOSE: Value          :
VERBOSE: 0000000000: 23 00 00 00 00 00 01 00 3b 52 3a c1 e7 62 ce 01
VERBOSE: 0x00000010: 26 45 00 00 00 00 00 00 00 00 00 00 00 00 00 00
VERBOSE: 0x00000020: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
VERBOSE: 0x00000030: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
VERBOSE: 0x00000040: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 78 00
VERBOSE: 0x00000050: 74 00 20 00 44 00 6f 00 63 00 75 00 6d 00 65 00
VERBOSE: 0x00000060: 6e 00 74 00 20 00 2d 00 20 00 43 00 6f 00 70 00
VERBOSE: 0x00000070: 79 00 20 00 28 00 31 00 30 00 29 00 2e 00 74 00
VERBOSE: 0x00000080: 78 00 74 00
VERBOSE: Corruption Record: 0x00030000000050b9
VERBOSE: Header:
VERBOSE: Version        : 1.0
VERBOSE: Flags          : (0x000000000000002c) GLOBALLY_VERIFIED | SKIP_SELF_HEALING | TESTED_DUPLICATE
VERBOSE: Length         : 74 bytes
VERBOSE: InstanceTag    : {00000000-0000-0000-0000-000000000000}
VERBOSE: description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
VERBOSE: Verb           : Connect
VERBOSE: Length         : 50 bytes
VERBOSE: Verb-Specific Fields:
VERBOSE: Index          :
VERBOSE: FRN            : 0x0001 0000`00000023
VERBOSE: Attribute:
VERBOSE: TypeCode: 0 Name: $I30
VERBOSE: Recover FRN    : 000000 0001`00000000
VERBOSE: FRN Count      : 1
VERBOSE: FRN 0 : 0x0001 0000`00000031
```

This command gets the volume corruption count for the computer on which you run the cmdlet.

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

### -DriveLetter
Specifies an array of letters that identify one or more drives or volumes in the system.
The cmdlet gets the volume corruption count for the drives or volumes you specify.

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
Specifies an array of file system labels.
The cmdlet gets the volume corruption count for the file system labels you specify.

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

### -ObjectId
Specifies an array of IDs, as strings.
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

### -Path
Specifies an array of paths.
The cmdlet gets the volume corruption count for the paths you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can use the pipeline operator to pass a Volume object to the *InputObject* parameter.

## OUTPUTS

### System.UInt32
This cmdlet returns the number of errors on the volume.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

