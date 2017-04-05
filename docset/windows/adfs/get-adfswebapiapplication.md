---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AdfsWebApiApplication

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Identifier (Default)
```
Get-AdfsWebApiApplication [[-Identifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsWebApiApplication [-Name] <String[]> [<CommonParameters>]
```

### PrefixIdentifier
```
Get-AdfsWebApiApplication [-PrefixIdentifier] <String> [<CommonParameters>]
```

### ApplicationObject
```
Get-AdfsWebApiApplication [-Application] <WebApiApplication> [<CommonParameters>]
```

### ApplicationGroupIdentifier
```
Get-AdfsWebApiApplication [-ApplicationGroupIdentifier] <String> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsWebApiApplication [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
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

### -Application
{{Fill Application Description}}

```yaml
Type: WebApiApplication
Parameter Sets: ApplicationObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Identifier
{{Fill Identifier Description}}

```yaml
Type: String[]
Parameter Sets: Identifier
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

### -PrefixIdentifier
{{Fill PrefixIdentifier Description}}

```yaml
Type: String
Parameter Sets: PrefixIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
Microsoft.IdentityServer.Management.Resources.WebApiApplication
System.String
Microsoft.IdentityServer.Management.Resources.ApplicationGroup

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

