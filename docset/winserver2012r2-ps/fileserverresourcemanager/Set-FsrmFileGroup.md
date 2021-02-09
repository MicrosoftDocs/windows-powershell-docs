---
external help file: FsrmFileGroup.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Set-FsrmFileGroup
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 656160DA-EE18-40B4-BC25-2EB76F5E0740
---

# Set-FsrmFileGroup

## SYNOPSIS
Changes configuration settings for file groups.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmFileGroup [-Name] <String[]> [-Description <String>] [-IncludePattern <String[]>]
 [-ExcludePattern <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmFileGroup -InputObject <CimInstance[]> [-Description <String>] [-IncludePattern <String[]>]
 [-ExcludePattern <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmFileGroup** cmdlet changes configuration settings for one or more file groups on the server.
The file group consists of two collections of wildcard patterns for file names.
One collection indicates file names that the server includes for file screens, and the other collection indicates file names that the server does not include for file screens.

## EXAMPLES

### Example 1: Change the include pattern of a file group
```
PS C:\>Set-FsrmFileGroup -Name "Media Files" -IncludePattern @("*.mp3", "*.wmv")
```

This command changes the file group named "Media Files".
After the cmdlet runs, the file group includes only files whose name ends in mp3 or wmv.

### Example 2: Change the include pattern of a file group by using an object variable
```
The first command gets the file group named "Media Files" and stored the results in the variable **$Group**.
PS C:\>$Group = Get-FsrmFileGroup "Media Files"

The second command specifies an include pattern that includes .wma files for the file group stored in the variable **$Group**. The command stores the result in the **$list** variable.
PS C:\>$list = $Group.IncludePattern + "*.wma"

The third command sets the include pattern for the file group named "Media Files" to the include pattern stored in the variable **$list**.
PS C:\>Set-FsrmFileGroup -Name "Media Files" -IncludePattern $list
```

This example changes the file group named "Media Files".
After the cmdlet runs, the file group also includes .wma files.

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
Specifies a description for the file group.

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

### -ExcludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The maximum size of a string is 1 KB.

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

### -IncludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The maximum size of a string is 1 KB.

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
Specifies an array of names of file groups.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileGroup

## NOTES

## RELATED LINKS

[Get-FsrmFileGroup](./Get-FsrmFileGroup.md)

[New-FsrmFileGroup](./New-FsrmFileGroup.md)

[Remove-FsrmFileGroup](./Remove-FsrmFileGroup.md)

