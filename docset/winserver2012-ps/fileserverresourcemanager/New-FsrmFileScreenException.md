---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 331ACAE2-7C05-49B0-9154-359D6DF9E82F
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-FsrmFileScreenException

## SYNOPSIS
Creates a file screen exception.

## SYNTAX

```
New-FsrmFileScreenException [-Path] <String> [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-IncludeGroup <String[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
**The New-FsrmFileScreenException** cmdlet creates a file screen exception.
A file screen exception is a special type of file screen that overrides any file screening that would otherwise apply to a folder, and all its subfolders, in a designated exception path.

A file screen exception creates an exception to any rules derived from a parent folder.
To determine which file types the exception allows, you can specify file groups for a file screen exception.

You cannot create a file screen exception on a folder for which you already have a file screen.
You must assign the exception to a subfolder or make changes to the existing file screen.

## EXAMPLES

### Example 1: Create a file screen exception
```
PS C:\>New-FsrmFileScreenException -Path "C:\Share1-IncludeGroup" -IncludeGroup "Text Files"
```

This command creates a file screen exception on C:\Share1-IncludeGroup that allows users to create files that are part of the "Text Files" file group.

## PARAMETERS

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
Specifies a description for a file screen exception.

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

### -Path
Specifies a valid local path to a folder.
The exception applies to the selected folder and all of its subfolders.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileScreenException

## NOTES

## RELATED LINKS

[Get-FsrmFileScreenException](./Get-FsrmFileScreenException.md)

[Set-FsrmFileScreenException](./Set-FsrmFileScreenException.md)

[Remove-FsrmFileScreenException](./Remove-FsrmFileScreenException.md)

