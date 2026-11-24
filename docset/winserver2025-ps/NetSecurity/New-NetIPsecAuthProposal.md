---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Firewall.Commands.dll-Help.xml
Module Name: NetSecurity
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/netsecurity/new-netipsecauthproposal?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIPsecAuthProposal
---

# New-NetIPsecAuthProposal

## SYNOPSIS
Creates a main mode authentication proposal that specifies a suite of authentication protocols to offer in IPsec main mode negotiations with other computers.

## SYNTAX

### HealthCert
```
New-NetIPsecAuthProposal [-AccountMapping] -Authority <String> [-AuthorityType <CertificateAuthorityType>]
 [-Cert] [-ExtendedKeyUsage <String[]>] [-ExcludeCAName] [-FollowRenewal] [-Health] [-Machine]
 [-SelectionCriteria] [-Signing <CertificateSigningAlgorithm>] [-SubjectName <String>]
 [-SubjectNameType <CertificateSubjectType>] [-Thumbprint <String>] [-ValidationCriteria] [<CommonParameters>]
```

### Cert
```
New-NetIPsecAuthProposal [-AccountMapping] -Authority <String> [-AuthorityType <CertificateAuthorityType>]
 [-Cert] [-ExtendedKeyUsage <String[]>] [-ExcludeCAName] [-FollowRenewal] [-SelectionCriteria]
 [-Signing <CertificateSigningAlgorithm>] [-SubjectName <String>] [-SubjectNameType <CertificateSubjectType>]
 [-Thumbprint <String>] [-User] [-ValidationCriteria] [<CommonParameters>]
```

### Anonymous
```
New-NetIPsecAuthProposal [-Anonymous] [<CommonParameters>]
```

### MachineKerb
```
New-NetIPsecAuthProposal [-Kerberos] [-Machine] [-Proxy <String>] [<CommonParameters>]
```

### UserKerb
```
New-NetIPsecAuthProposal [-Kerberos] [-Proxy <String>] [-User] [<CommonParameters>]
```

### MachineNTLM
```
New-NetIPsecAuthProposal [-Machine] [-Ntlm] [<CommonParameters>]
```

### PSK
```
New-NetIPsecAuthProposal [-Machine] [-PreSharedKey] <String> [<CommonParameters>]
```

### UserNTLM
```
New-NetIPsecAuthProposal [-Ntlm] [-User] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetIPsecAuthProposal** cmdlet creates a single authentication proposal to be used in IPsec main mode negotiations.
An authentication proposal describes a single authentication method that the computer would accept as valid proof of the identity of the peer.
This cmdlet is also used to authenticate the identity of the local user, so that a peer computer would accept the proof.

Multiple network IPsec authentication proposal fields are grouped into a single network IPsec phase 1 authentication set or network IPsec phase 2 authentication set.
Each set is a list of proposals in order of preference.
A phase 1 authentication is generally used for computer authentication, and a phase 2 authentication is used for user authentication or computer health certification.
See the New-NetIPsecPhase1AuthSet and New-NetIPsecPhase2AuthSet cmdlets for more information.
The authentication method, such as Kerberos v5, Certificate, or pre-shared key authentication, is provided by a network IPsec authentication proposal, specified through a network IPsec phase 1 authentication set, is required for a successful main mode security association.
See the Get-NetIPsecMainModeSA and Get-NetIPsecQuickModeSA cmdlets for more information.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$cert1Proposal = New-NetIPsecAuthProposal -Machine -Cert -Authority "C=US,O=MSFT,CN=ꞌMicrosoft Root Authorityꞌ" -AuthorityType Root



PS C:\>$cert2Proposal = New-NetIPsecAuthProposal -Machine -Cert -Authority "C=US,O=MYORG,CN='My Organizations Root Certificate'" -AuthorityType Root



PS C:\>$certAuthSet = New-NetIPsecPhase1AuthSet -DisplayName "Computer Certificate Auth Set" -Proposal $cert1Proposal,$cert2Proposal



PS C:\>New-NetIPSecRule -DisplayName "Authenticate with Certificates Rule" -InboundSecurity Require -OutboundSecurity Request -Phase2AuthSet $certAuthSet.Name
```

This example creates a rule that requires that incoming connections are authenticated by using either of two computer certificates.
The computer also requests authentication for outbound connections, but allows an outbound connection if authentication is not successful.

### EXAMPLE 2
```
PS C:\>$mkerbauthprop = New-NetIPsecAuthProposal -Machine -Kerberos



PS C:\>$mntlmauthprop = New-NetIPsecAuthProposal -Machine -NTLM



PS C:\>$p1Auth = New-NetIPsecPhase1AuthSet -DisplayName "First Machine Auth" -Proposal $mkerbauthprop,$mntlmauthprop



PS C:\>$ukerbauthprop = New-NetIPsecAuthProposal -User -Kerberos



PS C:\>$unentlmauthprop = New-NetIPsecAuthProposal -User -NTLM



PS C:\>$anonyauthprop = New-NetIPsecAuthProposal -Anonymous



PS C:\>$p2Auth = New-NetIPsecPhase2AuthSet -DisplayName "Second User Auth" -Proposal $ukerbauthprop,$unentlmauthprop,$anonyauthprop



PS C:\>New-NetIPSecRule -DisplayName "Authenticate Both Computer and User" -InboundSecurity Require -OutboundSecurity Require -Phase1AuthSet $p1Auth.Name -Phase2AuthSet $p2Auth.Name
```

This example creates a rule that requires a first, or computer, authentication and attempts an optional second, or user, authentication.

## PARAMETERS

### -AccountMapping
Specifies the enabled state for the IPsec certificate-to-account mapping.
In certificate-to-account mapping, the Internet Key Exchange (IKE) and AuthIP protocols associate, or map, a user or computer certificate to a user or computer account in an Active Directory (AD) domain or forest, and then retrieves an access token, which includes the list of user security groups.
This process ensures that the certificate offered by the IPsec peer corresponds to an active user or computer account in the domain, and that the certificate is one that should be used by that user or computer.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Anonymous
Specifies anonymous authentication.
Anonymous authentication means no authentication is performed.
This method does not require identity to authenticate.
It is equal to no authentication.
This provides end-to-end security between hosts, but does not provide any authentication or authorization for which users and computers can connect.
This method can be used for both phase 1 and phase 2 authentication.

```yaml
Type: SwitchParameter
Parameter Sets: Anonymous
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority
Specifies, for certificate authentication, the strong name, or X.509 string, of the Certification Authority (CA) that has issued the client certificates.
This parameter is used for certificate authentication.

```yaml
Type: String
Parameter Sets: HealthCert, Cert
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorityType
Specifies that certificates issued by intermediate CAs should be accepted.
This parameter is used for certificate authentication.
The acceptable values for this parameter are:: Root or Intermediate.
The default value is Root.
This parameter is supported in Windows Server® 2012.

```yaml
Type: CertificateAuthorityType
Parameter Sets: HealthCert, Cert
Aliases:
Accepted values: Invalid, Root, Intermediate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cert
Specifies that certificate authentication is used.
The *Authority* and *AuthorityType* parameters specify the certification authentication methods.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeCAName
Specifies that CA names are excluded.
This can only be specified for phase 1 authentications.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedKeyUsage
Specifies list of object identifiers (OIDs) that would be used on the extended key usage (EKU) field of a certificate.
When a CA issues a certificate, then the EKU specifies the intended purposes of the certificate.
For instance, there are specific OIDs for client-server communications as well as secure email and code signing.
An IPsec certificate can be selected or validated by EKU OID.
There is a limit of `100` EKUs.
This parameter is supported in Windows Server 2012.

```yaml
Type: String[]
Parameter Sets: HealthCert, Cert
Aliases: EKUs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FollowRenewal
Specifies that certificate signing is automatically renewed.
When the certificate is auto-renewed, the IPsec policy will not need to be updated.
This parameter only works for authentication methods that define a thumb print with the *Thumbprint* parameter.
This parameter only works, and is appropriate, for certificate selection methods.
The default value is False.
This parameter is supported in Windows Server 2012.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Health
Specifies that the certificate is a health certificate.
For phase 2 authentications, if the authentication method is only valid for computer certificates.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kerberos
Specifies that Kerberos is used.
This method authenticates the identity of user or computer accounts by using [Kerberos Protocol Extensions](https://msdn.microsoft.com/library/cc233855.aspx).

```yaml
Type: SwitchParameter
Parameter Sets: MachineKerb, UserKerb
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Machine
Specifies that the computer principal should be authenticated rather than the user.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, MachineKerb, MachineNTLM, PSK
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ntlm
Specifies that NTLM authentication is used.

```yaml
Type: SwitchParameter
Parameter Sets: MachineNTLM, UserNTLM
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreSharedKey
Specifies that the given pre-shared key is used for authentication.
The use of a pre-shared key is strongly discouraged, and is provided for interoperability and for conformance to IPsec standards.
The pre-shared key is stored in plain text.
The use of a more secure authentication method is strongly recommended.

```yaml
Type: String
Parameter Sets: PSK
Aliases: PSK

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy
Specifies the fully qualified domain name (FQDN) of the Kerberos proxy to use when authenticating from a remote network.
This parameter is supported in Windows Server 2012.

```yaml
Type: String
Parameter Sets: MachineKerb, UserKerb
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectionCriteria
Specifies that the current certificate authentication proposal should be used to select the certificate as offering to remote peers.
When using certificate criteria, exactly one proposal for selection and exactly one proposal for validation are needed.
A single proposal can be used for both.
If this parameter or the *ValidationCriteria* parameter is not specified, then the proposal is used for both.
This parameter is supported in Windows Server 2012.
The default value is False.
If both this parameter and the *ValidationCriteria* parameter are set to False, then the configuration is not valid and both flags in a new phase 1 authentication set or phase 2 authentication are set to True.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Signing
Specifies the certificate signing algorithm to accept.
The acceptable values for this parameter are: RSA, ECDSA256, or ECDSA384.
The default value is RSA.

```yaml
Type: CertificateSigningAlgorithm
Parameter Sets: HealthCert, Cert
Aliases:
Accepted values: Invalid, RSA, ECDSA256, ECDSA384

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubjectName
Determines, if it is not null, how the certificate should be validated.
A certification authority (CA) could put any string value into the Subject Name or Alternative Subject Name fields on a certificate, so there are no format requirements for this parameter.
However, depending on the value of SubjectNameType, there are some general formats that are usually followed.
Examine the certificates issued by the CA to find the exact formatting to use.
If the *SubjectNameType* parameter is:
- None: The Subject Name field on a certificate must be null.
- DomainName: The Subject Name field on a certificate should generally take the format of a FQDN.
The Alternative Subject Name field will be examined.
- UserPrincipalName: The Subject Name field on a certificate should generally take the format of an service principal name (SPN).
The Alternative Subject Name field will be examined.
- EmailAddress: An email address, like `username@contoso.com`.
The Alternative Subject Name field on a certificate will be examined.
- CN, OU, O, DC: The values from an X.509 strong name.
These will be parsed from the Subject Name field on a certificate.
This parameter is supported in Windows Server 2012.

```yaml
Type: String
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubjectNameType
Determines how the **SubjectName** field should be interpreted.
The acceptable values for this parameter are: None, DomainName, UserPrincipalName, EmailAddress, CN, OU, O, or DC.
This parameter is supported in Windows Server 2012.

```yaml
Type: CertificateSubjectType
Parameter Sets: HealthCert, Cert
Aliases:
Accepted values: None, DomainName, UserPrincipalName, EmailAddress, CN, OU, O, DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint hashing to use for certification criteria.
This is primarily intended for interoperability server-to-server authentication.
This parameter cannot be combined with the *FollowRenewal* parameter.
This parameter is supported in Windows Server 2012.

```yaml
Type: String
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies that the computer should authenticate as the user account, rather than the computer.
This parameter is valid with NTLM, Kerberos, Cert, or Proxy.

```yaml
Type: SwitchParameter
Parameter Sets: Cert, UserKerb, UserNTLM
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidationCriteria
For use with certificate criteria.
Specifies that the current certificate auth proposal should be used to validate the certificate given by the remote peer.
When using certificate criteria, exactly one proposal for selection and exactly one proposal for validation are needed.
A single proposal can be used for both.
If this parameter or the *SelectionCriteria* parameter is not specified, then the proposal is used for both.
This parameter is supported in Windows Server 2012.
The default value is False.
If both this parameter and the *SelectionCriteria* parameter are set to False, then the configuration is not valid and both flags in a new phase 1 authentication set or phase 2 authentication are set to True.

```yaml
Type: SwitchParameter
Parameter Sets: HealthCert, Cert
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIKEBasicAuthProposal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetIPsecMainModeSA](./Get-NetIPsecMainModeSA.md)

[New-NetIPsecPhase1AuthSet](./New-NetIPsecPhase1AuthSet.md)

[New-NetIPsecPhase2AuthSet](./New-NetIPsecPhase2AuthSet.md)

[New-NetIPSecRule](./New-NetIPsecRule.md)

