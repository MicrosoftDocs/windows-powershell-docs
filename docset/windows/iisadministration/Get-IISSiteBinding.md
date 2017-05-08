---
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-IISSiteBinding

## SYNOPSIS
Gets the bindings on the specified IIS site.

## SYNTAX

```
Get-IISSiteBinding [-Name] <String> [[-BindingInformation] <String>] [[-Protocol] <String>]
```

## DESCRIPTION
The **Get-IISSiteBinding** cmdlet gets information about web site bindings and their current status and other key information. 

## EXAMPLES

### Example 1: Get Information about an IIS website binding
```
PS C:\> Get-IISSiteBinding "Default Web Site" "*:80:" 
```

This command gets the binding information for the "*:80:" binding of the Default Web Site.

## Example 2: Get information about all bindings of an IIS website
```
PS C:\> Get-IISSiteBinding "Default Web Site"

protocol bindingInformation sslFlags
-------- ------------------ --------
http     *:80:                  None
http     *:1234:                None
```

This command gets all configuration information about all bindings of the Default Web Site

## PARAMETERS

### -BindingInformation
{{Fill BindingInformation Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
{{Fill Name Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Protocol
{{Fill Protocol Description}}

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

## INPUTS

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

