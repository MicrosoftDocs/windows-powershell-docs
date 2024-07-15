---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/add-certificateenrollmentpolicyserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-CertificateEnrollmentPolicyServer
---

# Add-CertificateEnrollmentPolicyServer

## SYNOPSIS

Adds an enrollment policy server to the current user or local system configuration.

## SYNTAX

```
Add-CertificateEnrollmentPolicyServer [-NoClobber] -Url <Uri> [-RequireStrongValidation]
 [-Credential <PkiCredential>] -context <Context> [-AutoEnrollmentEnabled] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Add-CertificateEnrollmentPolicyServer` cmdlet adds an enrollment policy server to the current
user or local system configuration. If an enrollment policy server already exists, then this cmdlet
will overwrite it. Group Policy can be configured to prevent enrollment policy servers from being
added.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing
user configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
Add-CertificateEnrollmentPolicyServer -Url $url -Context Machine
```

This example loads a policy from `$url` using Windows integrated authentication under the computer
context, using the computer account credentials. This example also adds the policy server to the
local computer configuration. Auto enrollment is off and strong validation is off.

### EXAMPLE 2

```powershell
$cert = Get-ChildItem -Path cert:\LocalMachine\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

$parameters = @{
    Url = $cert.EnrollmentPolicyEndPoint.Url
    Credential = $cert
    Context = 'Machine'
}
Add-CertificateEnrollmentPolicyServer @parameters
```

This example loads a policy using `$cert` as the authentication credential and adds the policy to
the local computer local configuration since the context is the local computer (Machine).

### EXAMPLE 3

```powershell
$up = Get-Credential

Add-CertificateEnrollmentPolicyServer -Url $url -Context Machine -Credential $up
```

This example loads a policy using the username and password from `$url`.
This example adds the policy server to the local computer configuration.

### EXAMPLE 4

```powershell
$cert = Get-ChildItem -Path cert:\CurrentUser\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

$parameters = @{
    Url = $cert.EnrollmentPolicyEnd
    Credential = $cert.PSPath
    Context = 'Machine'
}
Add-CertificateEnrollmentPolicyServer @parameters
```

This example loads policy using the Path object for a certificate. Use the certificate to
authenticate to the URL and add the policy server into the local user configuration.

### EXAMPLE 5

```powershell
$up = Get-Credential

Add-CertificateEnrollmentPolicyServer -Url $url -Context User -Credential $up -WhatIf
```

```Output
What if: Policy successfully loaded from {$url} using username/password credentials.
Policy server configuration will be added to current user context.
```

This example shows that if the policy cannot be loaded or if there is a conflict with an identifier
(ID) or URL, then this will be the output.

If the policy server already exists, then the output will state that the existing policy server
configuration will be overwritten.

## PARAMETERS

### -AutoEnrollmentEnabled

Enables auto-enrollment for the policy server being added.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Specifies the credential used to authenticate to the policy server. This credential can be a
**PSCredential** object, which is a username and password, an x509 certificate, or a path to an x509
certificate. Kerberos authentication is used if no credential is specified.

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

### -NoClobber

Prevents an enrollment policy server from overwriting an existing one.

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

### -RequireStrongValidation

Specifies that the certificate obtained through this enrollment policy server must be trusted on the
client.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Url

Identifies the uniform resource locator (URL) of the enrollment policy server to configure.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Context

Stores information about the policy server in the configuration for the Current User or Local
computer.

```yaml
Type: Microsoft.CertificateServices.Commands.Context
Parameter Sets: (All)
Aliases:
Accepted values: Machine, User

Required: True
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

### Microsoft.CertificateServices.Commands.EnrollmentPolicyServer

The **EnrollmentPolicyServer** object contains information about the certificate enrollment policy.

## OUTPUTS

### Microsoft.CertificateServices.Commands.EnrollmentPolicyServer

The **EnrollmentPolicyServer** object contains information about the certificate enrollment policy.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=290488)

[Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=293936)

[Get-CertificateEnrollmentPolicyServer](./Get-CertificateEnrollmentPolicyServer.md)

[Remove-CertificateEnrollmentPolicyServer](./Remove-CertificateEnrollmentPolicyServer.md)
