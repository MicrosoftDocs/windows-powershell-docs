---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsadditionalauthenticationrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAdditionalAuthenticationRule
---

# Set-AdfsAdditionalAuthenticationRule

## SYNOPSIS
Sets the global rules that provide the trigger for additional authentication providers to be invoked.

## SYNTAX

### RuleSets (Default)
```
Set-AdfsAdditionalAuthenticationRule [-AdditionalAuthenticationRules] <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RuleSetFile
```
Set-AdfsAdditionalAuthenticationRule [-AdditionalAuthenticationRulesFile] <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAdditionalAuthenticationRule** cmdlet sets the global rules that provide the trigger for additional authentication providers to be invoked.
When the claims engine evaluates the additional authentication rules and determines the requirement for multiple factor authentication, the user is prompted to perform additional authentication.
You may specify rules in the form of claim rules strings, or designate a file that contains claim rules.

Use this rule only when all your applications are capable of performing web based credential collection through Active Directory Federation Services (AD FS).
Applications that use protocols like WS-Trust will fail to obtain a security token if the trigger is true as a result of evaluation of the rules.

You can also set rules on the individual relying party trust using the **Set-AdfsRelyingPartyTrust** cmdlet with the **AdditionalAuthenticationRule** parameter.

## EXAMPLES

### Example 1: Set a global additional authentication rule
```
PS C:\> Set-AdfsAdditionalAuthenticationRule -AdditionalAuthenticationRules 'c:[type == "http://schemas.microsoft.com/ws/2012/01/insidecorporatenetwork", value == "false"] => issue(type = "http://schemas.microsoft.com/ws/2008/06/identity/claims/authenticationmethod", value = "http://schemas.microsoft.com/claims/multipleauthn" );'
```

This command sets an additional authentication rule to require multiple-factor authentication.

## PARAMETERS

### -AdditionalAuthenticationRules
Specifies rules for additional authentication.
For more information about the claims language for rules, see [Understanding Claim Rule Language in AD FS 2.0 & Higher](https://social.technet.microsoft.com/wiki/contents/articles/4792.understanding-claim-rule-language-in-ad-fs-2-0-higher.aspx) on TechNet.

```yaml
Type: String
Parameter Sets: RuleSets
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AdditionalAuthenticationRulesFile
Specifies the fully qualified file path of a text file that contains claim rules.

```yaml
Type: String
Parameter Sets: RuleSetFile
Aliases:

Required: True
Position: 0
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

[Get-AdfsAdditionalAuthenticationRule](./Get-AdfsAdditionalAuthenticationRule.md)

