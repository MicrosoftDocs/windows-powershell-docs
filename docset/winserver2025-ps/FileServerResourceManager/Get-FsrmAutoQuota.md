---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMAutoQuota.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmautoquota?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FsrmAutoQuota
---

# Get-FsrmAutoQuota

## SYNOPSIS
Gets auto apply quotas on a server.

## SYNTAX

```
Get-FsrmAutoQuota [[-Path] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmAutoQuota** cmdlet gets an auto apply quota or all auto apply quota on a volume or folder.
An auto apply quota is a quota template that you assign to a parent volume or folder.

## EXAMPLES

### Example 1: Get all auto apply quotas
```
PS C:\> Get-FsrmAutoQuota
```

This command gets all the auto apply quotas on the local server.

### Example 2: Get auto apply quotas by using a path
```
PS C:\> Get-FsrmAutoQuota -Path "C:\Share01\..."
```

This command gets all the auto apply quotas in C:\ Share01 plus all the auto apply quotas in all subfolders of C:\Share01.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Path
Specifies a valid local path to a folder.

This parameter supports recursive and wildcard paths.
To specify a recursive path, add \...
to a path.
For example, C:\ Share01\...
indicates all the auto apply quotas in C:\ Share1 plus all the auto apply quotas in any and all subfolders of C:\ Share01.

To specify a wildcard in a path, you can add the asterisk (*) and the question mark (?) to a path.
For example, C:\ Share01\*A indicates all the auto apply quotas in C:\ Share01 plus all the auto apply quotas in subfolders of C:\ Share01 that have a name that begins with the letter A.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMAutoQuota

## NOTES

## RELATED LINKS

[New-FsrmAutoQuota](./New-FsrmAutoQuota.md)

[Remove-FsrmAutoQuota](./Remove-FsrmAutoQuota.md)

[Set-FsrmAutoQuota](./Set-FsrmAutoQuota.md)

[Update-FsrmAutoQuota](./Update-FsrmAutoQuota.md)

