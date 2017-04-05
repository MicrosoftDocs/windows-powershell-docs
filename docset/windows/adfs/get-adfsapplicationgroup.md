---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AdfsApplicationGroup

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### ApplicationGroupIdentifier (Default)
```
Get-AdfsApplicationGroup [[-ApplicationGroupIdentifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsApplicationGroup [-Name] <String[]> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsApplicationGroup [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ApplicationGroup
{{Fill ApplicationGroup Description}}

```yaml
Type: ApplicationGroup
Parameter Sets: ApplicationGroupObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroupIdentifier
{{Fill ApplicationGroupIdentifier Description}}

```yaml
Type: String[]
Parameter Sets: ApplicationGroupIdentifier
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
{{Fill Name Description}}

```yaml
Type: String[]
Parameter Sets: Name
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

### System.String[]
Microsoft.IdentityServer.Management.Resources.ApplicationGroup

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

