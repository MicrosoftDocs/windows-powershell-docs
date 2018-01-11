---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: CBFB45D2-3658-41FA-BDEB-13920DF3908F
online version: 
schema: 2.0.0
---

# New-WebAppPool

## SYNOPSIS
Creates a new IIS application pool.

## SYNTAX

```
New-WebAppPool [-Name] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Creates a new IIS application pool.

## EXAMPLES

### -------------- EXAMPLE 1: Create new IIS Application Pool --------------
```
IIS:\>New-WebAppPool NewAppPool
```

This example creates a new IIS application pool named "NewAppPool."

## PARAMETERS

### -Force
Forces the operation without prompting

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

### -Name
The name of the IIS application pool to create.

```yaml
Type: String
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

