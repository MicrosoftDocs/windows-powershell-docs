---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMAutoQuota.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmautoquota?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmAutoQuota
---

# Set-FsrmAutoQuota

## SYNOPSIS
Changes configuration settings of an auto apply quota.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmAutoQuota [-Path] <String> [-Template <String>] [-Disabled] [-UpdateDerived] [-UpdateDerivedMatching]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmAutoQuota -InputObject <CimInstance[]> [-Template <String>] [-Disabled] [-UpdateDerived]
 [-UpdateDerivedMatching] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmAutoQuota** cmdlet changes configuration settings of an auto apply quota.
If you want to keep the existing quotas unchanged but make the modified auto apply quota effective for new subfolders in the auto apply quota path, do not specify either the *UpdateDerived* or *UpdateDerivedMatching* parameters.

When you make changes to an auto apply quota, you have the option of extending those changes to existing quotas in the auto apply quota path.
You can specify the *UpdateDerivedMatching* parameter to modify only those quotas that still match the original auto apply quota, or you can specify the *UpdateDerived* parameter to modify all quotas in the auto apply quota path, regardless of any modifications that you made to the quotas since you created them.

## EXAMPLES

### Example 1: Set the template for an auto apply quota
```
PS C:\> Set-FsrmAutoQuota -Path "C:\Shares\CtrShare01" -Template "200 MB Limit Reports to User"
```

This command sets the template named 200 MB Limit Reports to User for the auto apply quota on the folder named C:\Shares\CtrShare01.

### Example 2: Set the template for all quotas
```
PS C:\> Set-FsrmAutoQuota -Path "C:\Shares\CtrShare01" -Template "200 MB Limit Reports to User" -UpdateDerived
```

This command sets the template named 200 MB Limit Reports to User for all existing quotas in the auto apply quota path named C:\Shares\CtrShare01.

### Example 3: Set the template for unmodified quotas
```
PS C:\> Set-FsrmAutoQuota -Path "C:\Shares\CtrShare01" -Template "200 MB Limit Reports to User" -UpdateDerivedMatching
```

This command sets the template named 200 MB Limit Reports to User for only the quotas in the auto apply quota path named C:\Shares\CtrShare01 that have not been modified since they were automatically generated.

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

### -Disabled
Indicates that the auto apply quota is inactive.
The server does not track quota data for the quota and does not run any action associated with quota thresholds.

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

### -PassThru
Returns an object representing the item with which you are working.
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

### -Path
Specifies a valid local path to a folder.

```yaml
Type: String
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Template
Specifies a name of a quota template on the server.

```yaml
Type: String
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

### -UpdateDerived
Indicates that the server modifies all existing quotas in the auto apply quota path.

If you specify this parameter, you cannot specify the *UpdateDerivedMatching* parameter.

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

### -UpdateDerivedMatching
Indicates that the server updates only the quotas in the auto apply quota path that have not been modified since they were automatically generated.
Specify this parameter if you have quotas that have been modified since they were automatically generated, and you do not want to change them.

If you specify this parameter, you cannot specify the *UpdateDerived* parameter.

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

### System.String

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMAutoQuota

## NOTES

## RELATED LINKS

[Get-FsrmAutoQuota](./Get-FsrmAutoQuota.md)

[New-FsrmAutoQuota](./New-FsrmAutoQuota.md)

[Remove-FsrmAutoQuota](./Remove-FsrmAutoQuota.md)

[Update-FsrmAutoQuota](./Update-FsrmAutoQuota.md)

