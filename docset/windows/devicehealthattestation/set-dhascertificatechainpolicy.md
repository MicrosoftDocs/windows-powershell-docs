---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-DHASCertificateChainPolicy
ms.reviewer:
ms.assetid: 37C36EA7-9B95-42AA-B422-91D490ECC555
---

# Set-DHASCertificateChainPolicy

## SYNOPSIS
Sets certificate chain policy.

## SYNTAX

### SetCertificateChainPolicy (Default)
```
Set-DHASCertificateChainPolicy [-CertificateChainPolicy] <CertificateChainPolicy> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetCertificateChainPolicyComponents
```
Set-DHASCertificateChainPolicy -RevocationFlag <String> -RevocationMode <String> -VerificationFlags <String>
 -UrlRetrievalTimeout <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DHASCertificateChainPolicy** cmdlet sets the certificate chain policy that the Device Health Attestation service enforces.
The certificate chain policy specifies parameters for certificate chain verification and revocation behavior.

You can specify a **CertificateChainPolicy** object to use as input, or alternatively, you can specify the components that comprise a **CertificateChainPolicy**.
The components to specify as input are: 

- RevocationFlag. 
- RevocationMode. 
- VerificationFlags. 
- UrlRetrievalTimeout.

You must have administrator rights to run this cmdlets.

## EXAMPLES

### Example 1: Set certificate chain policy with a CertificateChainPolicy object
```
PS C:\> $policy = Get-DHASCertificateChainPolicy
PS C:\> $policy.RevocationFlag = "ExcludeRoot"
PS C:\> Set-DHASCertificateChainPolicy -CertificateChainPolicy $policy
```

The first command gets the **CertificateChainPolicy** object, and then stores it in the $policy variable.

The second command sets the RevocationFlag property of the policy to ExcludeRoot.

The third command sets the policy to include the new value for RevocationFlag.

### Example 2: Set certificate chain policy with its components
```
PS C:\> Set-DHASCertificateChainPolicy -RevocationFlag "ExcludeRoot" -RevocationMode "NoCheck" -VerificationFlags "NoFlag" -UrlRetrievalTimeout "00:01:00"
```

This command modifies the certificate chain policy by specifying a value for each of its components.

## PARAMETERS

### -CertificateChainPolicy
Specifies the certificate chain policy to use.

```yaml
Type: CertificateChainPolicy
Parameter Sets: SetCertificateChainPolicy
Aliases: 

Required: True
Position: 0
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

### -RevocationFlag
Specifies a .NET [X509RevocationFlag enumeration](http://go.microsoft.com/fwlink/?LinkId=821152).

```yaml
Type: String
Parameter Sets: SetCertificateChainPolicyComponents
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevocationMode
Specifies a .NET [X509RevocationMode enumeration](http://go.microsoft.com/fwlink/?LinkId=821153).

```yaml
Type: String
Parameter Sets: SetCertificateChainPolicyComponents
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UrlRetrievalTimeout
Specifies a .NET [TimeSpan structure](http://go.microsoft.com/fwlink/?LinkId=821155).

```yaml
Type: String
Parameter Sets: SetCertificateChainPolicyComponents
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VerificationFlags
Specifies a .NET [X509VerificationFlags enumeration](http://go.microsoft.com/fwlink/?LinkId=821154).

```yaml
Type: String
Parameter Sets: SetCertificateChainPolicyComponents
Aliases: 

Required: True
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CertificateChainPolicy

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DHASCertificateChainPolicy](./Get-DHASCertificateChainPolicy.md)

