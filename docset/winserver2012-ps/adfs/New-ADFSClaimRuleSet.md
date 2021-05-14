---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/new-adfsclaimruleset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ADFSClaimRuleSet

## SYNOPSIS
Creates a new set of claim rules.

## SYNTAX

### FromParams
```
New-ADFSClaimRuleSet -ClaimRule <String[]> [<CommonParameters>]
```

### FromFile
```
New-ADFSClaimRuleSet -ClaimRuleFile <String> [<CommonParameters>]
```

## DESCRIPTION
The New-ADFSClaimRuleSet cmdlet creates a new set of claim rules in Active Directory Federation Services (AD FS) 2.0.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$rSet = New-ADFSClaimRuleSet -ClaimRuleFile 'C:\ruleset.txt'
Set-ADFSRelyingPartyTrust -TargetName Fabrikam -IssuanceTransformRules $rSet.ClaimRulesString
```

Description

-----------

Creates a new claim rule set for a relying party trust using a text file.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$rSet = New-ADFSClaimRuleSet -ClaimRule 'c:[] => issue(claim = c);'
Set-ADFSRelyingPartyTrust -TargetName Fabrikam -IssuanceTransformRules $rSet.ClaimRulesString
```

Description

-----------

Creates a new claim rule set for a relying party trust using an inline AD FS 2.0 claims language rule.

## PARAMETERS

### -ClaimRule
Specifies the individual rules in this rule set.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimRuleSet
A class structure that represents a set of AD FS 2.0 claim rules.

## NOTES
* You can assign these claim rules to a claims provider trust or relying party trust by using the corresponding cmdlets.

## RELATED LINKS

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

