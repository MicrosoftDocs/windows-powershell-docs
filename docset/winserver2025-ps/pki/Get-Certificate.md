---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/get-certificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Certificate
---

# Get-Certificate

## SYNOPSIS
Submits a certificate request to an enrollment server and installs the response or retrieves a
certificate for a previously submitted request.

## SYNTAX

### SubmitRequest

```
Get-Certificate [-Url <Uri>] -Template <String> [-SubjectName <String>]
 [-DnsName <String[]>] [-Credential <PkiCredential>] [-CertStoreLocation <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PendingRetrieval

```
Get-Certificate -Request <Certificate> [-Credential <PkiCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-Certificate` cmdlet can be used to submit a certificate request and install the resulting
certificate, install a certificate from a pending certificate request, and enroll for LDAP. If the
request is issued, then the returned certificate is installed in the store determined by the
**CertStoreLocation** parameter and return the certificate in the **EnrollmentResult** structure
with status Issued. If the request is made pending, then the request is installed in the machine
REQUEST store and a request is returned in the **EnrollmentResult** structure with status Pending.

This cmdlet can be used in a Stateless mode where this cmdlet does not look up anything in the vault
or in a Stateful mode where it looks at registered certificate enrollment policy servers by
identifier (ID) and credential. When used with a request object and no credential, this cmdlet will
look up credentials in the vault based on the URL for the enrollment policy server.

This cmdlet will not accept a policy server identifier (ID). If a URL is not specified, then only
the default certificate enrollment policy ID is used and the cmdlet will attempt to obtain policy
information from any of its URLs.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing user
configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
$cred = Get-Credential

$params = @{
    Template = 'SslWebServer'
    DnsName = 'www.contoso.com', 'www.fabrikam.com'
    Url = 'https://www.contoso.com/Policy/service.svc'
    Credential = $cred
    CertStoreLocation = 'Cert:\LocalMachine\My'
}
Get-Certificate @params
```

This example submits a certificate request for the `SslWebServer` template to the specific URL using
the user name and password credentials. The request will have two DNS names in it. This is for a
certificate in the machine store. If the request is issued, then the returned certificate is
installed in the machine My store and the certificate in the **EnrollmentResult** structure is
returned with the status Issued. If the request is made pending, then the request is installed in
the machine REQUEST store and the request in the **EnrollmentResult** structure is returned with the
status Pending.

### EXAMPLE 2

```powershell
$cert = Get-ChildItem -Path cert:\LocalMachine\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

$params = @{
    Template = 'SslWebServer'
    DnsName = 'www.contoso.com'
    Url = 'https://www.contoso.com/policy/service.svc'
    Credential = $cert
    CertStoreLocation = 'Cert:\LocalMachine\My'
}
$enrollResult = Get-Certificate @params
```

This example submits a certificate request to a specific URL using the certificate credential for
authentication.

### EXAMPLE 3

```powershell
$params = @{
    Template = 'WorkstationTemplate'
    Url = 'https://www.contoso.com/service.svc'
}
Set-Location -Path Cert:\LocalMachine\My

$enrollResult = Get-Certificate @params
```

This example authenticates the URL using the machine account and Windows integrated authentication
and submits a request for a machine certificate of template named `WorkstationTemplate`.

### EXAMPLE 4

```powershell
Set-Location -Path Cert:\CurrentUser\My

Get-Certificate -Template User -Url ldap:
```

This example uses Windows integrated authentication to enroll for a certificate of template `User`
using direct DCOM calls to the Certificate Authority.

### EXAMPLE 5

```powershell
$request = Get-ChildItem -Path cert:\LocalMachine\Request\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

$cred = Get-Credential

Get-Certificate -Request $request -Credential $cred
```

This example retrieves and submits a pending request using a user name and password as credentials.

### EXAMPLE 6

```powershell
$request = Get-ChildItem -Path cert:\LocalMachine\Request\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

Get-Certificate -Request $request
```

This example retrieves the certificate identified by `$request`. If the authentication type for
`$request.EnrollmentServer.AuthType` is not Kerberos, then look in the credential store to see if
there is a credential for `$request.EnrollmentServer.Url`. If there is a credential, then use it. If
there is no credential, then Windows PowerShell will request it (if Windows PowerShell is in
Interactive mode).

## PARAMETERS

### -CertStoreLocation

Specifies the path to the certificate store for the received certificate.
If the request is made pending, then the request object is saved in the corresponding request store.

> [!NOTE]
> Only `My` store is supported.

```yaml
Type: System.String
Parameter Sets: SubmitRequest
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the credential to use for certificate enrollment. The credential can be a user name and
password (a credential object), an X509 certificate, or the path to a certificate. If a credential
is not specified, then Kerberos authentication is used.

```yaml
Type: Microsoft.CertificateServices.Commands.PkiCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsName

Specifies one or more DNS names to be included in the certificate request as subject alternative
name extension.

```yaml
Type: System.String[]
Parameter Sets: SubmitRequest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Request

Specifies the X509 certificate or the path to a requested certificate located in the request store.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: PendingRetrieval
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubjectName

Specifies the subject name to be included in the certificate request.

```yaml
Type: System.String
Parameter Sets: SubmitRequest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Template

Specifies the object identifier or name of a certificate template to use with the certificate
request.

```yaml
Type: System.String
Parameter Sets: SubmitRequest
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Url

Specifies the policy server URL to use for certificate enrollment. Credentials are required if the
endpoint requires a user name and password or certificate authentication from the client. If
credentials are not found and Windows PowerShell is in interactive mode, then a prompt for
credentials will appear.

```yaml
Type: System.Uri
Parameter Sets: SubmitRequest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2

The Certificate object can either be provided as a Path object to a certificate or an
**X509Certificate2** object.

### System.Uri

The **Uri** object can also be pipelined by the **Url** property name.

## OUTPUTS

### Microsoft.CertificateServices.Commands.EnrollmentResult

The **EnrollmentResult** object contains the results of enrollment.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=290488)

[Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=293936)

[Set-Location](https://go.microsoft.com/fwlink/p/?LinkId=293912)

[System Store Locations](/windows/desktop/seccrypto/system-store-locations)
