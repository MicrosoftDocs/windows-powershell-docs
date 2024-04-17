---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsnonclaimsawarerelyingpartytrust?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsNonClaimsAwareRelyingPartyTrust
---

# Remove-AdfsNonClaimsAwareRelyingPartyTrust

## SYNOPSIS
Removes a relying party trust for a non-claims-aware web application or service from the Federation Service.

## SYNTAX

### IdentifierName (Default)
```
Remove-AdfsNonClaimsAwareRelyingPartyTrust [-TargetName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Remove-AdfsNonClaimsAwareRelyingPartyTrust -TargetIdentifier <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsNonClaimsAwareRelyingPartyTrust
 [-TargetNonClaimsAwareRelyingPartyTrust <NonClaimsAwareRelyingPartyTrust>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsNonClaimsAwareRelyingPartyTrust** cmdlet removes a relying party trust for a non-claims-aware web application or service from the Federation Service.

A non-claims aware relying party trust is a relying party trust for web applications or services that do not rely directly on Active Directory Federation Services (AD FS) to issue tokens, but instead rely on a third party that accesses such tokens and transforms them into what applications understand.
A non-claims-aware relying party trust is useful for defining authentication and authorization policies for web applications and services that do not rely on AD FS tokens.
The Web Application Proxy requests such tokens for preauthentication to web applications or services that have corresponding non-claims-aware relying party trusts for requests that come from outside the network through the proxy.

## EXAMPLES

### Example 1: Remove a non-claims-aware relying party trust by using a name
```
PS C:\> Remove-AdfsNonClaimsAwareRelyingPartyTrust -TargetName "ExpenseReport"
```

This command removes the non-claims-aware relying party trust for the application named ExpenseReport.

### Example 1: Remove a non-claims-aware relying party trust by using an identifier
```
PS C:\> Remove-AdfsNonClaimsAwareRelyingPartyTrust -TargetIdentifier -TargetIdentifier "http://Contosoexpense/"
```

This command removes the non-claims-aware relying party trust for the expense report application that has the identifier http://Contosoexpense.

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

### -TargetIdentifier
Specifies the identifier of the non-claims-aware relying party trust to remove.

```yaml
Type: String
Parameter Sets: Identifier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the non-claims-aware relying party trust to remove.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetNonClaimsAwareRelyingPartyTrust
Specifies a **NonClaimsAwareRelyingPartyTrust** object.
The cmdlet removes the non-claims-aware relying party trust that you specify.
To obtain a **NonClaimsAwareRelyingPartyTrust**, use the Get-AdfsNonClaimsAwareRelyingPartyTrust cmdlet.

```yaml
Type: NonClaimsAwareRelyingPartyTrust
Parameter Sets: IdentifierObject
Aliases: 

Required: False
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

## NOTES

## RELATED LINKS

[Get-AdfsNonClaimsAwareRelyingPartyTrust](./Get-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Add-AdfsNonClaimsAwareRelyingPartyTrust](./Add-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Set-AdfsNonClaimsAwareRelyingPartyTrust](./Set-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Enable-AdfsNonClaimsAwareRelyingPartyTrust](./Enable-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Disable-AdfsNonClaimsAwareRelyingPartyTrust](./Disable-AdfsNonClaimsAwareRelyingPartyTrust.md)

