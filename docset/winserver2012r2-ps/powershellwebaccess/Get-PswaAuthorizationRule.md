---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-Help.xml
Module Name: PowerShellWebAccess
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/powershellwebaccess/get-pswaauthorizationrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PswaAuthorizationRule
---

# Get-PswaAuthorizationRule

## SYNOPSIS
Returns a set of the Windows PowerShell® Web Access authorization rules.

## SYNTAX

### ID (Default)
```
Get-PswaAuthorizationRule [[-Id] <Int32[]>] [<CommonParameters>]
```

### Name
```
Get-PswaAuthorizationRule [-RuleName] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-PswaAuthorizationRule** cmdlet returns a set of the Windows PowerShell® Web Access authorization rules. 

If neither the **Id** parameter nor the **RuleName** parameter is specified, then this cmdlet lists all rules.
The **Id** parameter can be used to filter the results.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-PswaAuthorizationRule
```

This example gets all of the rules.

### EXAMPLE 2
```
PS C:\> Get-PswaAuthorizationRule -Id 2
```

This example gets a rule with an ID of 2.

### EXAMPLE 3
```
PS C:\> "rule1",0 | Get-PswaAuthorizationRule
```

This example illustrates how the cmdlet accepts a value from pipeline.
A rule id and a rule name are passed in this cmdlet.

## PARAMETERS

### -Id
Specifies the identifiers (IDs) of the rules that this cmdlet should get.
If no IDs are specified, then this cmdlet returns all authorization rules.

```yaml
Type: Int32[]
Parameter Sets: ID
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RuleName
Specifies the names of authorization rules to retrieve.
This parameter returns any rules that exactly match the rule names of the strings in this array.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### int[], String[]
This cmdlet accepts an array of integers or an array of string values as input.

## OUTPUTS

### Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule[]
This cmdlet produces a PswaAuthorizationRule object as output.

## NOTES

## RELATED LINKS

[Add-PswaAuthorizationRule](./Add-PswaAuthorizationRule.md)

[Remove-PswaAuthorizationRule](./Remove-PswaAuthorizationRule.md)

[Test-PswaAuthorizationRule](./Test-PswaAuthorizationRule.md)

[Install-PswaWebApplication](./Install-PswaWebApplication.md)

