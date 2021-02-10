---
external help file: FsrmFileGroup.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Get-FsrmFileGroup
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 59B423DF-65F7-4090-A853-9D8B98793314
---

# Get-FsrmFileGroup

## SYNOPSIS
Gets file groups.

## SYNTAX

```
Get-FsrmFileGroup [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmFileGroup** cmdlet gets a file group or all file groups on the server.
A file group is a group of files that are based on one or more file name patterns.

## EXAMPLES

### Example 1: Get all file groups
```
PS C:\>Get-FsrmFileGroup
```

This command gets all files groups on the server.

### Example 2: Get a file group by using a name
```
PS C:\>Get-FsrmFileGroup -Name "Image Files"
```

This command gets the files group named "Image Files".

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

### -Name
Specifies an array of names of file groups.

```yaml
Type: String[]
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileGroup

## NOTES

## RELATED LINKS

[Set-FsrmFileGroup](./Set-FsrmFileGroup.md)

[New-FsrmFileGroup](./New-FsrmFileGroup.md)

[Remove-FsrmFileGroup](./Remove-FsrmFileGroup.md)

