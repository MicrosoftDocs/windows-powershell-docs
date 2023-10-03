---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/select-webconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Select-WebConfiguration

## SYNOPSIS
Returns Web configuration objects.

## SYNTAX

```
Select-WebConfiguration [-Filter] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Returns information about IIS configuration objects.

## EXAMPLES

### -------------- EXAMPLE 1: Get configuration settings --------------
```
IIS:\>Select-WebConfiguration "get-config(MACHINE/WEBROOT/APPHOST/testSite)/appSettings"
```

Returns the configuration collection from the appSettings location.
The specified location must exist or an error is returned.

## PARAMETERS

### -Filter
An XPath filter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
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

