---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientCertificateMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/remove-smbclientcertificatemapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbClientCertificateMapping
---

# Remove-SmbClientCertificateMapping

## SYNOPSIS
Removes an existing client certificate mapping for the Server Message Block (SMB) protocol.

## SYNTAX

### Query

```
Remove-SmbClientCertificateMapping [-Namespace] <String[]> [[-Subject] <String[]>]
 [[-Thumbprint] <String[]>] [[-DisplayName] <String[]>] [[-StoreName] <String[]>]
 [[-IssuerName] <String[]>] [[-Type] <Type[]>] [[-Flags] <Flags[]>] [-IncludeHidden] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Remove-SmbClientCertificateMapping -InputObject <CimInstance[]> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Remove-SmbClientCertificateMapping` cmdlet removes an existing client certificate mapping for
the SMB protocol. These mappings are used to authenticate clients that connect to SMB servers using
certificates. You can use this cmdlet to remove a mapping between a client certificate and an SMB
client name.

## EXAMPLES

### Example 1: Remove all certificate mappings from a specific store

```powershell
Remove-SmbClientCertificateMapping -StoreName "My" -Force
```

This force removes all certificate mappings that have been stored in a specific certificate store.

### Example 2: Remove a certificate mapping by thumbprint

```powershell
Remove-SmbClientCertificateMapping -Thumbprint "MyThumbprint" -Force
```

This force removes a certificate mapping with a specific thumbprint.

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
Parameter Sets: Query
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Flags

Specifies if Named Pipes are enabled for SMB over QUIC. The acceptable values for this parameter
are:

- `None`: Remove all flags.
- `AllowNamedPipe`: Enable use of named pipes in SMB over QUIC connections for this mapping (off by
  default, overrides the value of the **RestrictNamedPipeAccessOverQuic** parameter).
- `DefaultCert`: Not used.

```yaml
Type: Flags[]
Parameter Sets: Query
Aliases:
Accepted values: None, AllowNamedPipe, DefaultCert

Required: False
Position: 7
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

### -IncludeHidden

Not used.

```yaml
Type: SwitchParameter
Parameter Sets: Query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the input object that's used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssuerName

Filters the certificate mappings based on the issuer name of the certificate.

```yaml
Type: String[]
Parameter Sets: Query
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Specifies the namespace of the QUIC server. For example, `server1.contoso.com`. By default, the
cmdlet searches in the `root\cimv2\Security\MicrosoftTlsCertificateMappingProvider` namespace.

```yaml
Type: String[]
Parameter Sets: Query
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet doesn't
generate any output.

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

### -StoreName

Specifies the path to the certificate store for the certificate. The recommended value is "My" for
the local machine personal store.

```yaml
Type: String[]
Parameter Sets: Query
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject

Specifies the subject name of the certificate.

```yaml
Type: String[]
Parameter Sets: Query
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
Parameter Sets: Query
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type

`QUIC`: Certificate mapping is for SMB over QUIC.

```yaml
Type: Type[]
Parameter Sets: Query
Aliases:
Accepted values: QUIC

Required: False
Position: 6
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

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbClientCertificateMapping.Type[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbClientCertificateMapping.Flags[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbClientCertificateMapping

## NOTES

## RELATED LINKS

[Get-SmbClientCertificateMapping](Get-SmbClientCertificateMapping.md)

[New-SmbClientCertificateMapping](New-SmbClientCertificateMapping.md)

[Set-SmbClientCertificateMapping](Set-SmbClientCertificateMapping.md)
