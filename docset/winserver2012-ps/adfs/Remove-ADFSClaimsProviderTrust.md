---
author: Kateyanne
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
manager: dansimp
Module Name: ADFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adfs/remove-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ADFSClaimsProviderTrust

## SYNOPSIS
Removes a claims provider trust from the Federation Service.

## SYNTAX

### IdentifierObject
```
Remove-ADFSClaimsProviderTrust -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Remove-ADFSClaimsProviderTrust -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Identifier
```
Remove-ADFSClaimsProviderTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Remove-ADFSClaimsProviderTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-ADFSClaimsProviderTrust cmdlet removes a claims provider trust from the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-ADFSClaimsProviderTrust -TargetName "My claims provider"
```

Description

-----------

Removes the claims provider trust named "My claims provider".

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
Passes an object to the pipeline.
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

### -TargetCertificate
Specifies the token-signing certificate of the claims provider trust to remove.

```yaml
Type: X509Certificate2
Parameter Sets: TokenSigningCertificates
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClaimsProviderTrust
```yaml
Type: ClaimsProviderTrust
Parameter Sets: IdentifierObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the identifier of the claims provider trust to remove.

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
Specifies the name of the claims provider trust to remove.

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

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust
A class structure that represents a claims provider trust.

## OUTPUTS

### None

## NOTES
* The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Disable-ADFSClaimsProviderTrust](./Disable-ADFSClaimsProviderTrust.md)

[Enable-ADFSClaimsProviderTrust](./Enable-ADFSClaimsProviderTrust.md)

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

