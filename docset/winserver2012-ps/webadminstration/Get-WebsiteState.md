---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 2D2B23FF-81CF-4922-A7CD-443B2A6A0B36
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-WebsiteState

## SYNOPSIS
Gets the state of an IIS Web site.

## SYNTAX

```
Get-WebsiteState [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets the state of an IIS Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Get the state of a Web site --------------
```
IIS:\>Get-WebsiteState -Name "Default Web Site"
```

Returns the state of the Default Web Site.

Value

-----

Started

## PARAMETERS

### -Name
The name of the Web site to get information about.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

