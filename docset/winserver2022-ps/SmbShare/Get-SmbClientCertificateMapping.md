---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientCertificateMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbclientcertificatemapping?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbClientCertificateMapping
---

# Get-SmbClientCertificateMapping

## SYNOPSIS
Retrieves the client certificate mappings for the Server Message Block (SMB) protocol.

## SYNTAX

```
Get-SmbClientCertificateMapping [[-Namespace] <String[]>] [[-Subject] <String[]>]
 [-IssuerName <String[]>] [-Thumbprint <String[]>] [-DisplayName <String[]>] [-StoreName <String[]>]
 [-Type <Type[]>] [-Flags <Flags[]>] [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-SmbClientCertificateMapping` cmdlet retrieves the client certificate mappings for the SMB
protocol, such as when using SMB over QUIC. These mappings are used to authenticate clients that
connect to SMB servers using certificates.

## EXAMPLES

### Example 1: Retrieve all certificate mappings for a specific store

```powershell
Get-SmbClientCertificateMapping -StoreName "My"
```

This retrieves all certificate mappings that have been stored in a specific certificate store.

### Example 2: Retrieve a specific certificate mapping by display name

```powershell
Get-SmbClientCertificateMapping -DisplayName "MyCertificateMapping"
```

This retrieves a specific certificate mapping by its display name.

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

### -IncludeHidden

Not used.

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
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Specifies the namespace in which the certificate mappings are located. By default, the cmdlet
searches in the `root\cimv2\Security\MicrosoftTlsCertificateMappingProvider` namespace.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbClientCertificateMapping.Type[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbClientCertificateMapping.Flags[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbClientCertificateMapping

## NOTES

## RELATED LINKS

[New-SmbClientCertificateMapping](New-SmbClientCertificateMapping.md)

[Remove-SmbClientCertificateMapping](Remove-SmbClientCertificateMapping.md)

[Set-SmbClientCertificateMapping](Set-SmbClientCertificateMapping.md)
