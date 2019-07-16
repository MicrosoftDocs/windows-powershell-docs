---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: 
schema: 2.0.0
title: Export-RmsTUD
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: FF0D9DD1-4B65-41E0-B18F-614FD80BC779
---

# Export-RmsTUD

## SYNOPSIS
Exports a trusted user domain (TUD) in Active Directory Rights Management Services (AD RMS) to a file.

## SYNTAX

```
Export-RmsTUD [-SavedFile] <String[]> [-Force] [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Export-RmsTUD cmdlet exports the internal enterprise trusted user domain (TUD) in Active Directory Rights Management Services (AD RMS) to a file.

To perform the export, set the SavedFilePath parameter to the export file path, and then set the Path parameter to the AD RMS provider subpath "\<PSDrive\>:\TrustPolicy\TrustedUserDomain\\\<TUD_ID\>" where \<PSDrive\> is the provider drive ID and \<TUD_ID\> is the ID of the internal TUD.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Export-RmsTuD -Path .\100 -SavedFile c:\temp\test.xml
```

This command exports the TUD with the ID of 100 to the file c:\temp\test.xml.

## PARAMETERS

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

### -Force
Overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.
For example, Force will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SavedFile
Specifies the full path and filename of the file that receives the exported content.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](http://go.microsoft.com/fwlink/?LinkId=136806)

[Export-RmsTPD](./Export-RmsTPD.md)

[Import-RmsTPD](./Import-RmsTPD.md)

[Import-RmsTUD](./Import-RmsTUD.md)

