---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/update-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-ADFSClaimsProviderTrust

## SYNOPSIS
Updates the claims provider trust from federation metadata.

## SYNTAX

### IdentifierObject
```
Update-ADFSClaimsProviderTrust [-MetadataFile <String>] -TargetClaimsProviderTrust <ClaimsProviderTrust>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Update-ADFSClaimsProviderTrust [-MetadataFile <String>] -TargetCertificate <X509Certificate2> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Update-ADFSClaimsProviderTrust [-MetadataFile <String>] -TargetIdentifier <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Update-ADFSClaimsProviderTrust [-MetadataFile <String>] -TargetName <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Update-ADFSClaimsProviderTrust cmdlet updates the claims provider trust from federation metadata that is available at the federation metadata URL of the claims provider.
This cmdlet updates claims, endpoints, and certificates.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Update-ADFSClaimsProviderTrust -TargetName "My claims provider" -Identifier  https://contoso.com/adfs/ls/
```

Description

-----------

Update the identifier for an existing claims provider trust.

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

### -MetadataFile
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
Specifies the token-signing certificate of the claims provider trust to update.

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
Specifies the identifier of the claims provider trust to update.

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
Specifies the name of the claims provider trust to update.

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
* The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0 to use federation services, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

