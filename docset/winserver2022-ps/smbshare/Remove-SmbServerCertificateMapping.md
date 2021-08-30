---
external help file: SmbServerCertificateMapping.cdxml-help.xml
Module Name: SmbShare
online version:
schema: 2.0.0
---

# Remove-SmbServerCertificateMapping

## SYNOPSIS
Removes a certificate mapping from the SMB server for SMB over QUIC.

## SYNTAX

### Query
```
Remove-SmbServerCertificateMapping [-Name] <String[]> [[-Subject] <String[]>] [[-Thumbprint] <String[]>]
 [[-DisplayName] <String[]>] [[-StoreName] <String[]>] [[-Type] <Type[]>] [[-Flags] <Flags[]>] [-IncludeHidden]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-SmbServerCertificateMapping -InputObject <CimInstance[]> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-SmbServerCertificateMapping cmdlet removes a certificate’s mapping to the SMB server for SMB over QUIC on ‘Windows Server 2022 Datacenter: Azure Edition’. This cmdlet is not used for Windows or other Windows Server editions. For more information, review SMB over QUIC.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-SmbServerCertificateMapping
Name                        Subject       Thumbprint                               DisplayName StoreName Type Flags 
----                        -------       ----------                               ----------- --------- ---- ----- 
2022-ae-02.corp.contoso.com CN=2022-ae-02 88032B3551FAF7DE26EFFFF814AA086E3DBD2A4F 2022-ae-02  my        QUIC None 
fs2.contoso.com             CN=2022-ae-02 88032B3551FAF7DE26EFFFF814AA086E3DBD2A4F 2022-ae-02  my        QUIC None 

PS C:\> Remove-SmbServerCertificateMapping -name fs2.contoso.com -Thumbprint 88032B3551FAF7DE26EFFFF814AA086E3DBD2A4F 

Confirm 
Are you sure you want to perform this action? 
Performing operation 'Delete' on Target 'SMB Server Certificate Mapping.'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y 

PS C:\ >
```

This command removes a certificate mapping for SMB server edge endpoint “fs2.contoso.com” with a specific certificate thumbprint.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session object, such as the output of a New-CimSession or Get-CimSession cmdlet. The default is the current session on the local computer.

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
Specifies if Named Pipes are enabled for SMB over QUIC. The acceptable values for this parameter are: 

- **None** Remove all flags 
- **NamedPipes** Enable use of named pipes in SMB over QUIC connections for this mapping (off by default, overrides value of RestrictNamedPipeAccessOverQuic) 
- **DefaultCert** Not used

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
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate’s subject name or an entry in the certificate’s subject alternative names.

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
Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output.

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
Specifies the path to the certificate store for the certificate. The recommended value is “My” for the localmachine personal store.

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
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If this parameter is omitted or a value of 0 is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer. The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
**QUIC** Certificate mapping is for SMB over QUIC

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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Type[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Flags[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbServerCertificateMapping

## NOTES

## RELATED LINKS
