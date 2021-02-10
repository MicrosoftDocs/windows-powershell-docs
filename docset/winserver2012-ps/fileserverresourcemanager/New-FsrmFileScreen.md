---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 8ACACDB3-87C4-4CE0-85C2-769FCB9120D1
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-FsrmFileScreen

## SYNOPSIS
Creates a file screen.

## SYNTAX

```
New-FsrmFileScreen [-Path] <String> [-Active] [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-IncludeGroup <String[]>] [-Notification <CimInstance[]>] [-Template <String>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmFileScreen** cmdlet creates a file screen for a path on the server.
A file screen blocks users from saving groups of files to a specified folder.

If you specify the **Active** parameter, the file screen prevents users from saving files that are members of blocked file groups, and generates notifications when users try to save blocked files.
The file screen does not prevent users and applications from accessing files that were saved to the path before the file screen was created, regardless of whether the files are members of blocked file groups.

## EXAMPLES

### Example 1: Create a passive file screen
```powershell
PS C:\> New-FsrmFileScreen -Path "C:\Shares" -Description "Filter Non-HTML text files" -IncludeGroup "Non-HTML text files" -Active:$false
```

This command creates a passive file screen on C:\Shares that logs any files that match the "Non-HTML text files" file group.
The file screen template is passive because the command specifies the `-Active:$false` parameter.
This means that users can create non-HTML text files.

### Example 2: Create an active file screen
```powershell
PS C:\> $Notification = New-FsrmAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: attempted to create a non-HTML text file" -Body "You attempted to create a non-HTML text file. This is not allowed." -RunLimitInterval 120
PS C:\> New-FsrmFileScreen -Path "C:\Shares\Ctrshare03" -IncludeGroup "Non-HTML text files" -Notification $Notification -Active
```

The first command creates a File Server Resource Manager (FSRM) action object and stores the results in the $Notification variable.
The action sends an email notification to the file owner and administrator.
The **RunLimitInterval** parameter specifies an interval of 2 minutes before the server can send the email notification again.

This second command creates an active file screen on `C:\Shares\Ctrshare03` that restricts any files that match the "Non-HTML text files" file group.
When a user attempts to create a non-HTML text file, the file screen performs the notification action stored in the `$Notification` variable.

### Example 3: Create a file screen from a file screen template
```powershell
PS C:\> New-FsrmFileScreen -Path "C:\shares\ctrshare03" -Template "Block Image Files"
```

This command creates a file screen on `C:\shares\ctrshare03` based on the settings in the "Block Image Files" template.

## PARAMETERS

### -Active
Indicates that the server will fail any I/O operation that violates the file screen. It is enabled by default.

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

### -Path
Specifies a valid local path to a folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Template
Specifies a file screen template on the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

[Set-FsrmFileScreen](./Set-FsrmFileScreen.md)

[Reset-FsrmFileScreen](./Reset-FsrmFileScreen.md)

[Remove-FsrmFileScreen](./Remove-FsrmFileScreen.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

[Get-FsrmFileGroup](./Get-FsrmFileGroup.md)

