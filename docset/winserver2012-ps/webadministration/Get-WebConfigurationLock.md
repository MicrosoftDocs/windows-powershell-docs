---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigurationlock?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebConfigurationLock

## SYNOPSIS
Gets the lock status of the specified IIS configuration location.

## SYNTAX

```
Get-WebConfigurationLock [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets the locking status of the specified IIS configuration location.

## EXAMPLES

### -------------- EXAMPLE 1: Get the locking status of an IIS configuration --------------
```
IIS:\>Get-WebConfigurationLock -Filter //asp -PSPath IIS:\
```

Returns the locking status of theaspIIS configuration section.

## PARAMETERS

### -Filter
A filter expression.
It can be in XPath format.

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

### -Location
The location of the IIS configuration setting.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
An IIS configuration path in the formatcomputer name/webroot/apphost.

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

