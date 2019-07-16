---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 37258538-9859-42F9-921A-4FA172705C4A
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# New-FsrmFileGroup

## SYNOPSIS
Creates a file group.

## SYNTAX

```
New-FsrmFileGroup [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-ExcludePattern <String[]>] [-IncludePattern <String[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmFileGroup** cmdlet creates a file group object on the server.
A file group is a logical collection of file name patterns that the server uses to define file screens and file screen exceptions.
You can also use file group definitions for generating storage report jobs based on file type.

The file group consists of two collections of wildcard patterns for file names.
One collection indicates file names that the server includes for file screens, and the other collection indicates file names that the server does not include for file screens.

## EXAMPLES

### Example 1: Create a file group
```
PS C:\>New-FsrmFileGroup -Name "Non-HTML text files" -IncludePattern @("*.txt", "*ml") -ExcludePattern "*.html"
```

This command creates a file group named "Non-HTML text files".
The command indicates that files that end in txt or ml are included in the file group, and that files that end in .html are not included in the file group.

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
Specifies a description for the file group.

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

### -ExcludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The strings can be up to 1KB in size.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The strings can be up to 1KB in size.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the file group.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileGroup

## NOTES

## RELATED LINKS

[Get-FsrmFileGroup](./Get-FsrmFileGroup.md)

[Set-FsrmFileGroup](./Set-FsrmFileGroup.md)

[Remove-FsrmFileGroup](./Remove-FsrmFileGroup.md)

