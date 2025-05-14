---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfslocalclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsLocalClaimsProviderTrust
---

# Set-AdfsLocalClaimsProviderTrust

## SYNOPSIS
Modifies a local claims provider trust.

## SYNTAX

### IdentifierObject
```
Set-AdfsLocalClaimsProviderTrust [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-Name <String>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>] [-Force]
 -TargetClaimsProviderTrust <LocalClaimsProviderTrust> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Set-AdfsLocalClaimsProviderTrust [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-Name <String>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>] [-Force]
 -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Set-AdfsLocalClaimsProviderTrust [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-Name <String>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>] [-Force] -TargetName <String>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsLocalClaimsProviderTrust** cmdlet modifies a local claims provider trust.
For more information, see the **Add-AdfsLocalClaimsProviderTrust** cmdlet.

## EXAMPLES

## PARAMETERS

### -AcceptanceTransformRules
Specifies the set of claim rules to configure on the local claims provider trust.
These rules determine the information that is accepted from the partner represented by the local claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AcceptanceTransformRulesFile
Specifies the full path of a file that contains the set of claim rules to configure on the local claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies a name for the local claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies notes.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationalAccountSuffix
Specifies an array of organizational account suffixes that administrator can configure for the claims provider trust for a Home Realm Discovery (HRD) scenario.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### -TargetClaimsProviderTrust
Specifies the local claims provider trust to modify.
To obtain a **LocalClaimsProviderTrust** object, use the **Get-AdfsLocalClaimsProviderTrust** cmdlet.

```yaml
Type: LocalClaimsProviderTrust
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the local claims provider trust to modify.

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
Specifies the name of the local claims provider trust to modify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsLocalClaimsProviderTrust](./Add-AdfsLocalClaimsProviderTrust.md)

[Disable-AdfsLocalClaimsProviderTrust](./Disable-AdfsLocalClaimsProviderTrust.md)

[Enable-AdfsLocalClaimsProviderTrust](./Enable-AdfsLocalClaimsProviderTrust.md)

[Get-AdfsLocalClaimsProviderTrust](./Get-AdfsLocalClaimsProviderTrust.md)

[Remove-AdfsLocalClaimsProviderTrust](./Remove-AdfsLocalClaimsProviderTrust.md)

