---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: D5A72EDB-4E58-49A2-9EAE-4A3544B5FCB2
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WebVirtualDirectory

## SYNOPSIS
Gets a list of the virtual directories on the specified site.

## SYNTAX

```
Get-WebVirtualDirectory [-Site <String>] [-Application <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets a list of the virtual directories on the specified site.

## EXAMPLES

### -------------- EXAMPLE 1: Getting a virtual directory --------------
```
IIS:\>Get-WebVirtualDirectory -site 'Default Web Site' -Application testApp
```

This cmdlet returns the list of virtual directories on the Default Web Site on which the application named testApp is configured.

## PARAMETERS

### -Application
The name of a Web application with which virtual directories are associated.

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

### -Name
The name of a virtual directory to return.

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

### -Site
The name of the site for which a list of virtual directories is returned.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

