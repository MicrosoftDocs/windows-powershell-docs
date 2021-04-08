---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/get-webconfigurationlocation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebConfigurationLocation

## SYNOPSIS
Gets the location of a specified configuration setting.

## SYNTAX

```
Get-WebConfigurationLocation [[-Name] <String>] [-Recurse] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Gets the location of a specified configuration setting.

## EXAMPLES

### -------------- EXAMPLE 1: Get location tags --------------
```
IIS:\>Get-WebConfigurationLocation
```

Returns all locations that are configured by using location tags.

## PARAMETERS

### -Name
Specifies the name of the configuration location.
All locations are returned if theNameparameter is not specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
An IIS configuration path to the location.

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

### -Recurse
If theRecurseparameter is used, locations within the hierarchy of the specified location are also returned.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

