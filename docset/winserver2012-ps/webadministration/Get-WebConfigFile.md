---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/get-webconfigfile?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebConfigFile

## SYNOPSIS
Gets the file system path of the Web.config file.

## SYNTAX

```
Get-WebConfigFile [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Gets the physical path of the IIS configuration file at the specified IIS module namespace path.

## EXAMPLES

### -------------- EXAMPLE 1: Open the Web.config file for the Default Web Site --------------
```
IIS:\>notepad (Get-WebConfigFile 'IIS:\Sites\Default Web Site')
```

This example demonstrates how to use Notepad to open the web.config file for the Default Web Site.

## PARAMETERS

### -PSPath
The IIS module namespace path to the site containing the Web.config file.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

