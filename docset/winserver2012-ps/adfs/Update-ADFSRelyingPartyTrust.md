---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: FB6AE1D3-D601-45AA-BBEA-C56509664CF4
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Update-ADFSRelyingPartyTrust

## SYNOPSIS
Updates the relying party trust from federation metadata.

## SYNTAX

### Identifier
```
Update-ADFSRelyingPartyTrust [-MetadataFile <String>] -TargetIdentifier <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Update-ADFSRelyingPartyTrust [-MetadataFile <String>] -TargetRelyingParty <RelyingPartyTrust> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Update-ADFSRelyingPartyTrust [-MetadataFile <String>] -TargetName <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Update-ADFSRelyingPartyTrust cmdlet updates the relying party trust from the federation metadata that is available at the federation metadata URL.
This cmdlet updates claims, endpoints, and certificates.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Update-ADFSRelyingPartyTrust -TargetName "Sample App"
```

Description

-----------

Updates a relying party trust object.

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

### -TargetIdentifier
Specifies the identifier of the relying party trust to update.

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
Specifies the name of the relying party trust to update.

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
Specifies the relying party trust to update.
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

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust
A class structure that represents a relying party trust.

## OUTPUTS

### None

## NOTES
* A relying party in Active Directory Federation Services (AD FS) 2.0 is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately consumed by the Web-based resources that are located in the relying party organization. When AD FS 2.0 is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party consumes the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server at the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-ADFSRelyingPartyTrust](./Add-ADFSRelyingPartyTrust.md)

[Disable-ADFSRelyingPartyTrust](./Disable-ADFSRelyingPartyTrust.md)

[Enable-ADFSRelyingPartyTrust](./Enable-ADFSRelyingPartyTrust.md)

[Get-ADFSRelyingPartyTrust](./Get-ADFSRelyingPartyTrust.md)

[Remove-ADFSRelyingPartyTrust](./Remove-ADFSRelyingPartyTrust.md)

[Set-ADFSRelyingPartyTrust](./Set-ADFSRelyingPartyTrust.md)

