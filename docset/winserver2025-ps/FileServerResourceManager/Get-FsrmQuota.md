---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmQuota.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmquota?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FsrmQuota
---

# Get-FsrmQuota

## SYNOPSIS
Gets FSRM quotas on the server.

## SYNTAX

```
Get-FsrmQuota [[-Path] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmQuota** cmdlet gets a File Server Resource Manager (FSRM) quota or all FSRM quotas on the server.

## EXAMPLES

### Example 1: Get all quotas
```
PS C:\> Get-FsrmQuota
```

This command gets all quotas on the server.

### Example 2: Get quotas by using a path
```
PS C:\> Get-FsrmQuota -Path "C:\Share01\..."
```

This command gets all of the quotas in C:\Share01 plus all of the quotas in all subfolders of C:\Share01.

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
Specifies the local folder that contains the quota.

This parameter supports recursive and wildcard paths.
To specify a recursive path, add \...
to a path.
For example, C:\Share01\...
indicates all of the quotas in C:\Share01 plus all the quotas in any and all subfolders of C:\Share01.
To specify a wildcard in a path, you can add the asterisk (&ast;) and the question mark (?) to a path.
For example, C:\Share01\*A indicates all of the quotas in C:\Share01 plus all the quotas in subfolders of C:\Share01 that have a name that begins with the letter A.

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

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMQuota

## NOTES

## RELATED LINKS

[New-FsrmQuota](./New-FsrmQuota.md)

[Remove-FsrmQuota](./Remove-FsrmQuota.md)

[Reset-FsrmQuota](./Reset-FsrmQuota.md)

[Set-FsrmQuota](./Set-FsrmQuota.md)

[Update-FsrmQuota](./Update-FsrmQuota.md)

