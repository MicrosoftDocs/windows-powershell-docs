---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: Nps
online version: 
schema: 2.0.0
title: Export-NpsConfiguration
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CF8BA4DF-3B15-436C-AFD3-97A2B69764BB
ms.author: kenwith
ms.reviewer: brianlic
---

# Export-NpsConfiguration

## SYNOPSIS
Exports NPS settings.

## SYNTAX

```
Export-NpsConfiguration [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Export-NpsConfiguration** cmdlet exports settings for Network Policy Server (NPS).
NPS manages network access policies for client health, connection request authentication, and connection request authorization.
You can use NPS as a Remote Authentication Dial-In User Service (RADIUS) proxy to forward connection requests to NPS or other RADIUS servers that you configure in remote RADIUS server groups.
For more information about NPS, see Network Policy Serverhttp://technet.microsoft.com/en-us/library/cc732912.aspx (http://technet.microsoft.com/en-us/library/cc732912.aspx) on TechNet.

The exported file contains unencrypted shared secrets for RADIUS clients and members of remote RADIUS server groups.
Because of this, make sure that you save the file to a secure location.

The export process does not include Logging settings for Microsoft SQL Server in the exported file.
After you import the exported file to another NPS server, you must manually configure SQL Server Logging on the new server.

## EXAMPLES

### Example 1: Export settings from a Network Policy Server to a file
```
PS C:\>Export-NpsConfiguration -Path C:\Npsconfig.xml
```

This command exports settings from NPS to the file named C:\Npsconfig.xml.

## PARAMETERS

### -Path
Specifies the full path of the export file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS


