---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFSConfiguration

## SYNOPSIS
Gets the configuration properties of the Federation Service.

## SYNTAX

```
Get-ADFSConfiguration [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSConfiguration cmdlet gets the configuration properties of the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Get-ADFSConfiguration
```

Gets the current settings for all configuration properties of the Federation Service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceProperties
A class structure that represents the properties for the Federation Service.

## NOTES
* The ADFSConfiguration resource enumerates the current configuration properties and settings used by the Federation Service.

## RELATED LINKS

[Set-ADFSConfiguration](./Set-ADFSConfiguration.md)

