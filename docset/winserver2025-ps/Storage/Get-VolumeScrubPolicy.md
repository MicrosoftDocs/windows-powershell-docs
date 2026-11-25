---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Volume.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-volumescrubpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VolumeScrubPolicy
---

# Get-VolumeScrubPolicy

## SYNOPSIS
Gets the status of the volume scrub policy.

## SYNTAX

### ByDriveLetter (Default)
```
Get-VolumeScrubPolicy [-DriveLetter] <Char[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ById
```
Get-VolumeScrubPolicy -ObjectId <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPaths
```
Get-VolumeScrubPolicy -Path <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByLabel
```
Get-VolumeScrubPolicy -FileSystemLabel <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-VolumeScrubPolicy -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VolumeScrubPolicy** cmdlet gets the status of the volume scrub policy.

## EXAMPLES

### Example 1: Get the volume scrub policy
```
PS C:\>Get-Volume H | Set-VolumeScrubPolicy -Enable $False
PS C:\> Get-VolumeScrubPolicy H
```

This command sets the volume scrub policy to $False, and then gets the volume scrub policy to verify the change.

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
The cmdlet gets the volume scrub policy for the drives or volumes you specify.

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
The cmdlet gets the volume scrub policy for the file system labels you specify.

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
The cmdlet gets the volume scrub policy for the paths you specify.

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

### System.Boolean
This cmdlet returns the whether the volume scrub policy is true or false.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Volume](./Get-Volume.md)

[Set-VolumeScrubPolicy](./Set-VolumeScrubPolicy.md)

