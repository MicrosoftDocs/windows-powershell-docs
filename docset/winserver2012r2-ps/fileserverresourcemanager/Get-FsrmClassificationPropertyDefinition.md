---
external help file: FSRMClassificationPropertyDefinition.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Get-FsrmClassificationPropertyDefinition
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 570B5DBE-164F-441A-A5E9-84B82F07E3A8
---

# Get-FsrmClassificationPropertyDefinition

## SYNOPSIS
Gets definitions of classification properties.

## SYNTAX

```
Get-FsrmClassificationPropertyDefinition [[-Name] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmClassificationPropertyDefinition** cmdlet gets one or more definitions of classification properties.
The server uses classification properties to assign values to files.

This cmdlet automatically attempts, up to once an hour, to get any updated property definitions for Active Directory Domain Service (AD DS).
You can use the Update-FsrmClassificationPropertyDefinition cmdlet to force the server to update the property definitions more often.

## EXAMPLES

### Example 1: Get all classification property definitions
```
PS C:\>Get-FsrmClassificationPropertyDefinition
```

This command gets all classification property definitions on the server.

### Example 2: Get a classification property definition by using a name
```
PS C:\>Get-FsrmClassificationPropertyDefinition -Name "PII_MS"
```

This command gets the classification property definition named "PII_MS".

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
Specifies an array of names of property definitions.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMClassificationPropertyDefinition

## NOTES

## RELATED LINKS

[Set-FsrmClassificationPropertyDefinition](./Set-FsrmClassificationPropertyDefinition.md)

[New-FsrmClassificationPropertyDefinition](./New-FsrmClassificationPropertyDefinition.md)

[Update-FsrmClassificationPropertyDefinition](./Update-FsrmClassificationPropertyDefinition.md)

[Remove-FsrmClassificationPropertyDefinition](./Remove-FsrmClassificationPropertyDefinition.md)

