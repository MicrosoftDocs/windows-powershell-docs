---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-Help.xml
Module Name: PowerShellWebAccess
online version: 
schema: 2.0.0
title: Remove-PswaAuthorizationRule
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A90BBDF3-0B7F-422F-B3CA-070CEB44D19B
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Remove-PswaAuthorizationRule

## SYNOPSIS
Removes a specified authorization rule from Windows PowerShell® Web Access.

## SYNTAX

### ID (Default)
```
Remove-PswaAuthorizationRule [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Rule
```
Remove-PswaAuthorizationRule [-Rule] <PswaAuthorizationRule[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes a specified authorization rule from Windows PowerShell Web Access.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-PswaAuthorizationRule -Id 2
```

This example removes the authorization rule with an ID of 2.

### EXAMPLE 2
```
PS C:\> Get-PswaAuthorizationRule | Remove-PswaAuthorizationRule -Confirm
```

This example removes all authorization rules and also requires confirmation by the user.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet asks for confirmation before proceeding.

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

### -Id
Specifies the identifiers (IDs) of one or more rules to remove.

```yaml
Type: Int32[]
Parameter Sets: ID
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Rule
Specifies the rules to remove.

```yaml
Type: PswaAuthorizationRule[]
Parameter Sets: Rule
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### int[], PswaAuthorizationRule[]
This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-PswaAuthorizationRule](./Add-PswaAuthorizationRule.md)

[Get-PswaAuthorizationRule](./Get-PswaAuthorizationRule.md)

[Test-PswaAuthorizationRule](./Test-PswaAuthorizationRule.md)

[Install-PswaWebApplication](./Install-PswaWebApplication.md)

