---
description: Extends the Active Directory (AD) schema with the Windows Local Administrator Password Solution (LAPS) schema attributes.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/update-lapsadschema?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Update-LapsADSchema
---

# Update-LapsADSchema

## SYNOPSIS
Extends the Active Directory (AD) schema with the Windows Local Administrator Password Solution
(LAPS) schema attributes.

## SYNTAX

```
Update-LapsADSchema [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Update-LapsADSchema` cmdlet extends the AD schema with the LAPS schema attributes. The specific
nature of the schema extensions is documented in
[Windows LAPS schema extensions reference](https://go.microsoft.com/fwlink/?linkid=2233804).

The **Verbose** parameter may be used to get additional information about the cmdlet's operation.

## EXAMPLES

### Example 1

```powershell
Update-LapsADSchema
```

```Output
The 'ms-LAPS-Password' schema attribute needs to be added to the AD schema.
Do you want to proceed?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
```

This example extends the AD schema to add the LAPS attributes.

## PARAMETERS

### -Credential

Specifies a set of credentials to use when extending the schema. If not specified, the current
user's credentials are used.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)

[Windows LAPS schema extensions reference](https://go.microsoft.com/fwlink/?linkid=2233804)
