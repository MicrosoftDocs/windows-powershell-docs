---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/debug-volume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Volume
---

# Debug-Volume

## SYNOPSIS
Finds problems with a volume and recommends solutions.

## SYNTAX

### ByDriveLetter (Default)
```
Debug-Volume [-DriveLetter] <Char[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ById
```
Debug-Volume -ObjectId <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPaths
```
Debug-Volume -Path <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLabel
```
Debug-Volume -FileSystemLabel <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject
```
Debug-Volume -InputObject <CimInstance> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Debug-Volume** cmdlet finds problems with a volume and recommends solutions.

## EXAMPLES

### Example 1: Debug a volume
```
PS C:\>Get-Volume | ? {?_.HealthStatus -ne "Healthy"} | Debug-Volume
```

This cmdlet gets the status of volumes where the **HealthStatus** property does not equal Healthy, and uses the pipeline operator to pass those volumes to the **Debug-Volume** cmdlet.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetter
Specifies an array of letters that identify one or more drives or volumes in the system.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies an array of file system labels.

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Specifies an array of object IDs, as strings.

```yaml
Type: String[]
Parameter Sets: ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies an array of valid paths.

```yaml
Type: String[]
Parameter Sets: ByPaths
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageDiagnoseResult

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[New-Volume](./New-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)

