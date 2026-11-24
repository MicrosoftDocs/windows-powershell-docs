---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsclaimruleset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsClaimRuleSet
---

# New-AdfsClaimRuleSet

## SYNOPSIS
Creates a set of claim rules.

## SYNTAX

### FromParams
```
New-AdfsClaimRuleSet -ClaimRule <String[]> [<CommonParameters>]
```

### FromFile
```
New-AdfsClaimRuleSet -ClaimRuleFile <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsClaimRuleSet** cmdlet creates a set of claim rules in Active Directory Federation Services (AD FS) 2.0.

## EXAMPLES

### Example 1: Create a claim rule set by using a text file
```
PS C:\> $RuleSet = New-AdfsClaimRuleSet -ClaimRuleFile 'C:\ruleset.txt'
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "Fabrikam" -IssuanceTransformRules $RuleSet.ClaimRulesString
```

The first command creates a claim rule set by using a text file, and then stores it in the $RuleSet variable.

The second command uses the **Set-AdfsRelyingPartyTrust** cmdlet to assign the rule set stored in $RuleSet to a relying party trust.
The command refers to the **ClaimsRuleString** property of the object stored in $RuleSet.

### Example 2: Create a claim rule set by using an inline rule
```
PS C:\> $RuleSet = New-AdfsClaimRuleSet -ClaimRule 'c:[] => issue(claim = c);'
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "Fabrikam" -IssuanceTransformRules $RuleSet.ClaimRulesString
```

The first command creates a claim rule set by using an inline AD FS 2.0 claims language rule, and then stores it in the $RuleSet variable.

The second command uses **Set-AdfsRelyingPartyTrust** to assign the rule set stored in $RuleSet to a relying party trust.
The command refers to the **ClaimsRuleString** property of the object stored in $RuleSet.

## PARAMETERS

### -ClaimRule
Specifies an array of individual rules in this rule set.

```yaml
Type: String[]
Parameter Sets: FromParams
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClaimRuleFile
Specifies the serialized policy text that is created by the collection of rules in the rule set.

```yaml
Type: String
Parameter Sets: FromFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimRuleSet
This cmdlet generates a class structure that represents a set of AD FS 2.0 claim rules.

## NOTES
* You can assign these claim rules to a claims provider trust or relying party trust by using the corresponding cmdlets.

## RELATED LINKS

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

