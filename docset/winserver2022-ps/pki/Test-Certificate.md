---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/test-certificate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Certificate
---

# Test-Certificate

## SYNOPSIS
Verifies a certificate according to the input parameters.

## SYNTAX

```
Test-Certificate [-Policy <TestCertificatePolicy>] [-User] [-EKU <String[]>]
 [-DNSName <String>] [-AllowUntrustedRoot] [-Cert] <Certificate> [<CommonParameters>]
```

## DESCRIPTION

The `Test-Certificate` cmdlet verifies a certificate according to input parameters. The revocation
status of the certificate is verified by default. If the **AllowUntrustedRoot** parameter is
specified, then a certificate chain is built but an untrusted root is allowed. Other errors are
still verified against in this case, such as expired. If the **DNSName** parameter is used, then the
DNS subject alternative name is used to verify SSL policy. If the **EKU** parameter is used, then
the specified application policy object identifiers are used to verify the chain. If the **User**
parameter is used, then the specified user context is used is to build and verify the chain.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing user
configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-ChildItem -Path Cert:\LocalMachine\My |
    Test-Certificate -Policy SSL -DNSName 'dns=contoso.com'
```

This example verifies each certificate in the MY store of the local machine and verifies that it is
valid for SSL with the DNS name specified.

### EXAMPLE 2

```powershell
$params = @{
    Cert = 'Cert:\CurrentUser\My\191C46F680F08A9E6EF3F6783140F60A979C7D3B'
    AllowUntrustedRoot = $true
    EKU = '1.3.6.1.5.5.7.3.1'
    User = $true
}
Test-Certificate @params
```

This example verifies that the provided EKU is valid for the specified certificate and its chain.
Revocation checking is not performed.

## PARAMETERS

### -AllowUntrustedRoot

Specifies whether the root certificate is required to be trusted in chain building. When this
parameter is used, the certificate chain is built but an untrusted root is allowed. Other errors are
still verified against in this case, such as expired. If this parameter is not specified, then
revocation status is checked by default.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cert

Specifies the certificate to test. Either the certificate object or a path to the certificate in a
certificate store can be specified.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: (All)
Aliases: PsPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DNSName

Specifies the DNS name to verify as valid for the certificate.

If this parameter is specified but not the **Policy** parameter, then the `CERT_CHAIN_POLICY_SSL`
policy is applied and the DNS name is validated for the certificate. If a `CERT_CHAIN_POLICY_SSL`
policy does not exist, then the cmdlet will fail.

If this parameter is not used and the **Policy** parameter is not specified, the default
`CERT_CHAIN_POLICY_BASE` policy is applied.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EKU

Specifies a list of enhanced key usage (EKU) object identifiers to verify for the certificate chain.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy

Specifies the policies that will be applied to verify the certificate. The acceptable values for
this parameter are: `AUTHENTICODE`, `BASE`, `NTAUTH`, and `SSL`. If this parameter is not specified,
then the `BASE` policy is used.

```yaml
Type: Microsoft.CertificateServices.Commands.TestCertificatePolicy
Parameter Sets: (All)
Aliases: 
Accepted values: BASE, SSL, AUTHENTICODE, NTAUTH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User

Specifies whether the user or machine context is used to test the certificate. If this parameter is
not specified, then the machine context is used.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.Certificate

The **Certificate** object can either be provided as a Path object to a certificate or an
**X509Certificate2** object.

## OUTPUTS

### System.Boolean

If the verification succeeds, then the return value is True; otherwise the return value is False.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=290488)
