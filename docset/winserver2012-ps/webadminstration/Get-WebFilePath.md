---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 2664F7E9-259B-4179-A247-7E1943CB3D21
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WebFilePath

## SYNOPSIS
Gets the physical path to the location of the specified IIS module.

## SYNTAX

```
Get-WebFilePath [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Gets the physical path to the location of the specified IIS module.

## EXAMPLES

### -------------- EXAMPLE 1: Get the physical path of the Default Web Site --------------
```
IIS:\>Get-WebFilePath 'IIS:\Sites\Default Web Site'
```

Demonstrates how to retrieve the physical path for the Default Web Site.

Directory: Microsoft.PowerShell.Core\FileSystem::C:\inetpub

Mode LastWriteTime Length Name

---- ------------- ------ ----

d---- 7/28/2008 9:40 PM wwwroot

## PARAMETERS

### -PSPath
An IIS configuration path.

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

