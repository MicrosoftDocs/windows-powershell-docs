---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsKeyProtection
ms.assetid: 66EB835B-1521-4350-81B5-75F297C169CD
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-HgsKeyProtectionAttestationSignerCertificate
ms.reviewer:
---

# Remove-HgsKeyProtectionAttestationSignerCertificate

## SYNOPSIS
Removes an attestation signer certificate from the trusted certificates in the Key Protection Service.

## SYNTAX

```
Remove-HgsKeyProtectionAttestationSignerCertificate -Thumbprint <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsKeyProtectionAttestationSignerCertificate** cmdlet removes the signer certificate of an attestation server from the attestation signer certificates that the Key Protection Service trusts.

## EXAMPLES

### Example 1: Remove an attestation certificate
```
PS C:\> Remove-HgsKeyProtectionAttestationSignerCertificate -Thumbprint "d39203a3b3544743ad552afe0615dc1f"
```

This command removes a trusted attestation certificate signer.
The command looks up the certificate signer to remove by using a thumbprint.

## PARAMETERS

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

### -Thumbprint
Specifies the thumbprint of the attestation signer certificate to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-HgsKeyProtectionAttestationSignerCertificate](./Add-HgsKeyProtectionAttestationSignerCertificate.md)

[Get-HgsKeyProtectionAttestationSignerCertificate](./Get-HgsKeyProtectionAttestationSignerCertificate.md)

