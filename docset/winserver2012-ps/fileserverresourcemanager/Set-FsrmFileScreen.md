---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: AE603879-72CE-4D9D-BA0B-5205AB7347D9
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-FsrmFileScreen

## SYNOPSIS
Changes configuration settings of a file screen.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmFileScreen [-Path] <String> [-Active] [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-IncludeGroup <String[]>] [-Notification <CimInstance[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmFileScreen [-Active] [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-IncludeGroup <String[]>] [-Notification <CimInstance[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmFileScreen** cmdlet changes configuration settings of a file screen on the server.
A file screen blocks users from saving groups of files on a volume or in a folder tree.

If you specify the **Active** parameter, the file screen prevents users from saving files that are members of blocked file groups, and generates notifications when users try to save blocked files.
The file screen does not prevent users and applications from accessing files that were saved to the path before the file screen was created, regardless of whether the files are members of blocked file groups.

## EXAMPLES

### Example 1: Change the include group for a file screen
```
PS C:\>Set-FsrmFileScreen -Path "C:\share1" -IncludeGroup @("Media Files", "Text Files")
```

This command changes the file screen on c:\share1 to include both Media Files and Text Files.

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

### -Description
Specifies a description for the file screen.

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
Specifies an array of names of file groups.
The file groups contain the file name patterns that the server uses to specify the files that are blocked by this screen.

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

### -Path
Specifies a valid local path to a folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileScreen

## NOTES

## RELATED LINKS

[Get-FsrmFileScreen](./Get-FsrmFileScreen.md)

[New-FsrmFileScreen](./New-FsrmFileScreen.md)

[Reset-FsrmFileScreen](./Reset-FsrmFileScreen.md)

[Remove-FsrmFileScreen](./Remove-FsrmFileScreen.md)

[Get-FsrmFileGroup](./Get-FsrmFileGroup.md)

