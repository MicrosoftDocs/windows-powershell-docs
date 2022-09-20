---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adfs/disable-adfsrelyingpartytrust?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AdfsRelyingPartyTrust
---

# Disable-AdfsRelyingPartyTrust

## SYNOPSIS
Disables a relying party trust of the Federation Service.

## SYNTAX

### Identifier
```
Disable-AdfsRelyingPartyTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Disable-AdfsRelyingPartyTrust -TargetRelyingParty <RelyingPartyTrust> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierName
```
Disable-AdfsRelyingPartyTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AdfsRelyingPartyTrust** cmdlet disables a relying party trust of the Federation Service.
When disabled, AD FS does not issue tokens when users attempt to access this relying party.

## EXAMPLES

### 1:
```

```

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -TargetIdentifier
Specifies the identifier of the relying party trust to disable.

```yaml
Type: String
Parameter Sets: Identifier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the relying party trust to disable.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetRelyingParty
Specifies the relying party trust to disable.
This value is typically taken from the pipeline.

```yaml
Type: RelyingPartyTrust
Parameter Sets: IdentifierObject
Aliases: 

Required: True
Position: Named
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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

