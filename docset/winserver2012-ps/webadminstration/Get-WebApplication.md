---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 76C3A941-6AAB-4F53-ACE4-F7FDA7244E7D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-WebApplication

## SYNOPSIS
Gets the Web Applications associated with a specific site or with the specified name.

## SYNTAX

```
Get-WebApplication [-Site <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets the Web applications associated with a specific site or with the specified name.

## EXAMPLES

### -------------- EXAMPLE 1: Gets the Web applications associated with the Default Web Site --------------
```
IIS:\>Get-WebApplication -Site "Default Web Site"
```

Gets the Web applications associated with the Default Web Site.

## PARAMETERS

### -Name
The name of the Web application.

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
The Site name for which application information is returned.

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

