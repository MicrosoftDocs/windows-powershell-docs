---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientCertificateMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbclientcertificatemapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbClientCertificateMapping
---

# New-SmbClientCertificateMapping

## SYNOPSIS
Creates a new client certificate mapping for the Server Message Block (SMB) protocol.

## SYNTAX

```
New-SmbClientCertificateMapping [-Namespace] <String> [-Thumbprint <String>] [-StoreName <String>]
 [-IssuerName <String>] [-Subject <String>] [-DisplayName <String>] [-Type <Type>] [-Flags <Flags>]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `New-SmbClientCertificateMapping` cmdlet creates a new client certificate mapping for the SMB
protocol. These mappings are used to authenticate clients that connect to SMB servers using
certificates. You can use this cmdlet to create a new mapping between a client certificate and an
SMB client name.

## EXAMPLES

### Example 1: Create a new certificate mapping for an SMB client

```powershell
$params = @{
    Thumbprint = "a1b2c3d4e5f6g7h8"
    StoreName = "My"
    IssuerName = "CN=MyCertificateAuthority"
    Subject = "CN=MyClientCertificate"
    DisplayName = "MyClientCertificateMapping"
}
New-SmbClientCertificateMapping @params
```

This creates a new certificate mapping for an SMB client where a specific thumbprint, store name,
issuer name, subject, and display name are specified for the certificate mapping.

For example, if you have an SMB client named `MySMBClient` that needs to connect to a server using
a specific certificate, you could use this cmdlet to create a certificate mapping that associates
the client with the certificate.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Specifies the friendly name of the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Flags

Specifies if `NamedPipes` are enabled for SMB over QUIC. The acceptable values for this parameter
are:

- `None`: Remove all flags
- `AllowNamedPipe`: Enable use of named pipes in SMB over QUIC connections for this mapping (off by
  default, overrides value of the **RestrictNamedPipeAccessOverQuic** parameter)
- `DefaultCert`: Not used

```yaml
Type: Flags[]
Parameter Sets: (All)
Aliases:
Accepted values: None, AllowNamedPipe, DefaultCert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -IssuerName

Filters the certificate mappings based on the issuer name of the certificate.

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

### -Namespace

Specifies the namespace of the QUIC server. For example, `server1.contoso.com`. By default, the
cmdlet searches in the `root\cimv2\Security\MicrosoftTlsCertificateMappingProvider` namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoreName

Specifies the path to the certificate store for the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject

Specifies the subject name of the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint

Specifies the thumbprint value of the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type

Specifies the type of certificate mapping. The acceptable value for this parameter is:

`QUIC`: Certificate mapping is for SMB over QUIC.

```yaml
Type: Type[]
Parameter Sets: (All)
Aliases:
Accepted values: QUIC

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-SmbClientCertificateMapping](Get-SmbClientCertificateMapping.md)

[Remove-SmbClientCertificateMapping](Remove-SmbClientCertificateMapping.md)

[Set-SmbClientCertificateMapping](Set-SmbClientCertificateMapping.md)
