---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmFileScreenTemplate.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmfilescreentemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmFileScreenTemplate
---

# Set-FsrmFileScreenTemplate

## SYNOPSIS
Changes configuration settings of a file screen template.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmFileScreenTemplate [-Name] <String[]> [-Description <String>] [-IncludeGroup <String[]>] [-Active]
 [-UpdateDerived] [-UpdateDerivedMatching] [-Notification <CimInstance[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmFileScreenTemplate -InputObject <CimInstance[]> [-Description <String>] [-IncludeGroup <String[]>]
 [-Active] [-UpdateDerived] [-UpdateDerivedMatching] [-Notification <CimInstance[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmFileScreenTemplate** cmdlet changes configuration settings of a file screen template.

When you make changes to a file screen template, you have the option of extending those changes to existing file screens that were created with the original file screen template.
You can specify the *UpdateDerivedMatching* parameter to modify only those quotas that still match the original file screen template, or you can specify the *UpdateDerived* parameter to modify all file screens that were created with the original file screen template, regardless of any modifications that you made to the file screens.

## EXAMPLES

### Example 1: Change the include group for a file screen template
```
PS C:\> Set-FsrmFileScreenTemplate -Name "Filter Media files" -IncludeGroup @("Media Files", "Text Files")
```

This command changes a file screen template named "Filter Media files" to include both media files and text files.

### Example 2: Changes the include group for a file screen template and derived file screen templates
```
PS C:\> Set-FsrmFileScreenTemplate "1GB limit" -IncludeGroup @("Media Files", "Text Files") -UpdateDerived
```

This command updates a file screen template named "1GB limit" to include both media files and text files.
The server also updates these settings in any file screens that derive from this template.

## PARAMETERS

### -Active
Indicates that the server fails any I/O operation that violates the file screen.
If you do not specify this parameter, the server does not fail violating I/O operations and still runs any action that is associated with the file screen.

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

### -Description
Specifies a description for the file screen template.

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

### -IncludeGroup
Specifies an array of names of file groups that you want to exclude from file screening.

```yaml
Type: String[]
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

### -Name
Specifies the name of a file screen template.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Notification
Specifies an array of notification action objects.
You can use the **New-FsrmFmjNotificationAction** cmdlet to create a **FsrmFmjNotificationAction** object.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Indicates that the server modifies all existing file screens that were created with the original file screen template.
If you specify this parameter, you cannot specify the *UpdateDerivedMatching* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpdateDerivedMatching
Indicates that the server updates only the file screens that you have not modified since you created them with the original file screen template.
If you specify this parameter, you cannot specify the *UpdateDerived* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FsrmFileScreenTemplate

## NOTES

## RELATED LINKS

[Get-FsrmFileScreenTemplate](./Get-FsrmFileScreenTemplate.md)

[New-FsrmFileScreenTemplate](./New-FsrmFileScreenTemplate.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

[Remove-FsrmFileScreenTemplate](./Remove-FsrmFileScreenTemplate.md)

