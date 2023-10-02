---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/enable-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-ADFSClaimsProviderTrust

## SYNOPSIS
Enables a claims provider trust in the Federation Service.

## SYNTAX

### IdentifierObject
```
Enable-ADFSClaimsProviderTrust -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Enable-ADFSClaimsProviderTrust -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Identifier
```
Enable-ADFSClaimsProviderTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Enable-ADFSClaimsProviderTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Enable-ADFSClaimsProviderTrust cmdlet enables a claims provider trust in the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Enable-ADFSClaimsProviderTrust -TargetName "My claims provider"
```

Description

-----------

Enables a claims provider trust with the name "My claims provider".

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
Specifies the token-signing certificate of the claims provider trust to enable.

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
Specifies the identifier of the claims provider trust to enable.

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
Specifies the name of the claims provider trust to enable.

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
A class structure that represents the claims provider trusts for the Federation Service.

## OUTPUTS

### None

## NOTES
* The claims provider is responsible for collecting and authenticating a user's credentials, building up claims for that user, and packaging the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0  to use federation services, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Disable-ADFSClaimsProviderTrust](./Disable-ADFSClaimsProviderTrust.md)

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Remove-ADFSClaimsProviderTrust](./Remove-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

