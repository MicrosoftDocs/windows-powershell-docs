---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmfilescreentemplate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-FsrmFileScreenTemplate

## SYNOPSIS
Changes configuration settings of a file screen template.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmFileScreenTemplate [-Name] <String[]> [-Active] [-AsJob] [-CimSession <CimSession[]>]
 [-Description <String>] [-IncludeGroup <String[]>] [-Notification <CimInstance[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-UpdateDerived] [-UpdateDerivedMatching] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmFileScreenTemplate [-Active] [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-IncludeGroup <String[]>] [-Notification <CimInstance[]>] [-PassThru] [-ThrottleLimit <Int32>]
 [-UpdateDerived] [-UpdateDerivedMatching] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmFileScreenTemplate** cmdlet changes configuration settings of a file screen template.

When you make changes to a file screen template, you have the option of extending those changes to existing file screens that were created with the original file screen template.
You can specify the **UpdateDerivedMatching** parameter to modify only those quotas that still match the original file screen template, or you can specify the **UpdateDerived** parameter to modify all file screens that were created with the original file screen template, regardless of any modifications that you made to the file screens.

## EXAMPLES

### Example 1: Change the include group for a file screen template
```
PS C:\>Set-FsrmFileScreenTemplate -Name "Filter Media files" -IncludeGroup @("Media Files", "Text Files")
```

This command changes a file screen template named "Filter Media files" to include both media files and text files.

### Example 2: Changes the include group for a file screen template and derived file screen templates
```
PS C:\>Set-FsrmFileScreenTemplate "1GB limit" -IncludeGroup @("Media Files", "Text Files") -UpdateDerived
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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Notification
Specifies an array of notification action objects.
You can use the New-FsrmFmjNotificationAction cmdlet to create a **FsrmFmjNotificationAction** object.

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
If you specify this parameter, you cannot specify the **UpdateDerivedMatching** parameter.

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
If you specify this parameter, you cannot specify the **UpdateDerived** parameter.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileScreenTemplate

## NOTES

## RELATED LINKS

[Get-FsrmFileScreenTemplate](./Get-FsrmFileScreenTemplate.md)

[New-FsrmFileScreenTemplate](./New-FsrmFileScreenTemplate.md)

[Remove-FsrmFileScreenTemplate](./Remove-FsrmFileScreenTemplate.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

