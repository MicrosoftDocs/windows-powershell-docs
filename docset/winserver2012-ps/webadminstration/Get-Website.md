---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 2F185688-C463-48A1-AA28-908DA4FA71DA
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-Website

## SYNOPSIS
Gets configuration information for an IIS Web site.

## SYNTAX

```
Get-Website [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets configuration information for an IIS Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Get information about the Default Web Site --------------
```
IIS:\>Get-Website -Name "Default Web Site"
```

Returns the configuration information for the Default Web Site.

Name ID State Physical Path Bindings

---- -- ----- ------------- --------

Default Web Site 1 Started%SystemDrive%\inetpub\wwwroot http *:80:

net.tcp 808:*

## PARAMETERS

### -Name
The name of the Web site about which configuration information is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

