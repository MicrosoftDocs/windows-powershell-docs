---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerCertificateMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/remove-smbservercertificatemapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbServerCertificateMapping
---

# Remove-SmbServerCertificateMapping

## SYNOPSIS
Removes a certificate mapping from the SMB server for SMB over QUIC.

## SYNTAX

### Query

```
Remove-SmbServerCertificateMapping [-Name] <String[]> [[-Subject] <String[]>]
 [[-Thumbprint] <String[]>] [[-DisplayName] <String[]>] [[-StoreName] <String[]>] [[-Type] <Type[]>]
 [[-Flags]<Flags[]>] [[-RequireClientAuthentication] <Boolean[]>]
 [[-SkipClientCertificateAccessCheck] <Boolean[]>] [-IncludeHidden] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Remove-SmbServerCertificateMapping -InputObject <CimInstance[]> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Remove-SmbServerCertificateMapping` cmdlet removes the certificates associated with the SMB
server for SMB over QUIC. For more information, review
[SMB over QUIC](/windows-server/storage/file-server/smb-over-quic).

> [!NOTE]
>
> - If the **RequireClientAuthentication** parameter is set to `$true` and
> **SkipClientCertificateAccessCheck** is set to `$false`, the server will perform both client
> certificate validation and access control checks.
>
> - If the **RequireClientAuthentication** parameter is set to `$true` and
> **SkipClientCertificateAccessCheck** is also set to `$true`, the server will perform client
> certificate validation but no access control checks.

## EXAMPLES

### Example 1 - Remove a certificate mapping for SMB server edge endpoint

```powershell
$params = @{
    Name = "fs2.contoso.com"
    Thumbprint = "88032B3551FAF7DE26EFFFF814AA086E3DBD2A4F"
}
Remove-SmbServerCertificateMapping @params
```

```output
Confirm
Are you sure you want to perform this action?
Performing operation 'Delete' on Target 'SMB Server Certificate Mapping.'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes a certificate mapping for SMB server edge endpoint `fs2.contoso.com` with a
specific certificate thumbprint.

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
object, such as the output of a [`New-CimSession`](/powershell/module/cimcmdlets/new-cimsession) or
[`Get-CimSession`](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
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

Specifies a friendly name to display for the mapping.

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
  default, overrides the value of RestrictNamedPipeAccessOverQuic).
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

### -Name

Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate's subject name
or an entry in the certificate's subject alternative names.

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

### -RequireClientAuthentication

Specifies whether client authentication is required for connections to the server. When this
parameter is set to `$true`, clients must present a valid certificate to connect to the server.
When it is set to `$false`, clients can connect without presenting a certificate.

```yaml
Type: Boolean[]
Parameter Sets: Query
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipClientCertificateAccessCheck

Specifies whether the server should skip the check for client certificate access when a client
connects. This parameter only applies when the server certificate mapping
**RequireClientAuthentication** value is `$true`. When this parameter is set to `$true`, the server
will not perform the access control checks based on the client certificates. This can be useful in
scenarios where the server is acting as a gateway or proxy and client certificate validation is
sufficient.

However, it can also increase the risk of security breaches. When this parameter is set to
`$false`, the server will perform the access control checks based on the client certificates in
addition to the client certificate validation before allowing the client to connect.

```yaml
Type: Boolean[]
Parameter Sets: Query
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Specifies the type of certificate mapping. The acceptable value for this parameter is:

- `QUIC`: Certificate mapping is for SMB over QUIC.

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
Default value: None
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
Default value: None
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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Type[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Flags[]

### System.Boolean[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbServerCertificateMapping

## NOTES

## RELATED LINKS

[Get-SmbServerCertificateMapping](Get-SmbServerCertificateMapping.md)

[New-SmbServerCertificateMapping](New-SmbServerCertificateMapping.md)

[Set-SmbServerCertificateMapping](Set-SmbServerCertificateMapping.md)
